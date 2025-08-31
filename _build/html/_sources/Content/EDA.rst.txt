.. _EDA:

Exploratory Data Analysis
===========================

Several Exploratory Data Analysis (EDA) processes were conducted to understand the condition of the dataset, such as checking for missing values, duplicate data, and data distribution based on labels. The EDA steps implemented included:

Label Distribution in Train and Test Sets
-----------------------------------------

The code snippet below is used to create and display a bar chart showing the distribution of data in the train set and test set based on each label.

.. code-block:: python

   import matplotlib.pyplot as plt

   # Merge train and test datasets
   df_combined = pd.concat([df_train.assign(dataset='Train'), df_test.assign(dataset='Test')], axis=0)

   # Calculate label distribution for each dataset
   train_counts = df_combined[df_combined['dataset'] == 'Train']['labels'].value_counts().sort_index()
   test_counts = df_combined[df_combined['dataset'] == 'Test']['labels'].value_counts().sort_index()

   # Plotting
   plt.figure(figsize=(10, 6))
   width = 0.35  # Bar width

   train_indices = range(len(train_counts))
   test_indices = [i + width for i in train_indices]

   plt.bar(train_indices, train_counts, width=width, label='Train', color='blue', alpha=0.7)
   plt.bar(test_indices, test_counts, width=width, label='Test', color='orange', alpha=0.7)

   plt.xlabel('Condition Label')
   plt.ylabel('Number of Samples')
   plt.title('Data Distribution by Condition Label (Train vs Test)')
   plt.xticks([i + width / 2 for i in train_indices], train_counts.index)
   plt.legend(title='Dataset')
   plt.tight_layout()
   plt.show()


Duplicate Data Check
--------------------

This code snippet is used to display the number of duplicate data instances in the dataset.

.. code-block:: python

   # checking for duplicate data
   print(df_train.duplicated().sum())
   print(df_test.duplicated().sum())


Missing Values Check
--------------------

This code snippet is used to display the number of data instances that have empty values (missing values) in certain columns. In this case, the check is performed on the text and labels columns.

.. code-block:: python

   # checking for missing values
   print(df_train.isna().sum())
   print(df_test.isna().sum())


Word Count Analysis
-------------------

This code is used to count the number of words in the text for each data instance. The results of the calculation are stored in a new column called “Word Count,” which represents the number of words in each line of text. Next, the average, minimum, maximum, and other statistics can be viewed using the “describe()” function.

.. code-block:: python

   from nltk.tokenize import word_tokenize
   import nltk
   nltk.download('punkt')

   df_eda = df_train.copy()

   # Function to count the number of words in a text
   def word_count(text):
       words = word_tokenize(text)
       return len(words)

   # Adding a word count column to a DataFrame
   df_eda['Word Count'] = df_eda['text'].apply(word_count)

   # Displaying a DataFrame with the number of words column
   print(df_eda.head())

   # Descriptive statistics for Word Count
   print(df_eda['Word Count'].describe())
