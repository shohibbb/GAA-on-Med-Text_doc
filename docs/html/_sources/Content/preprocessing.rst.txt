.. _preprocessing:

Pre-processing
==============

In this paper, there are several pre-processing steps executed to prepare the dataset for use in analytical and classificatory purposes. 
The following steps were applied: 

Case Folding
-------------

The first pre-processing step is case folding, which converts all text characters into lowercase form. 
This helps maintain consistency across the dataset by eliminating differences between uppercase and lowercase letters.  

In addition, the function below also removes unnecessary whitespace, such as multiple spaces or irregular spacing 
around apostrophes. This ensures the text is more uniform and easier to process in later stages.

.. code-block:: python

   def preprocess_text(text):
       text = text.lower()  # Convert to lowercase
       text = re.sub(r'\s+', ' ', text)
       text = re.sub(r"\s*'\s*", "'", text)
       text = text.strip()  # Remove leading and trailing whitespace
       return text

   df['text'] = df['text'].apply(preprocess_text)

Data Splitting
--------------

Split data into two parts namely training data and test data with a splitting range of 80:20 
for traditional machine learning algorithms and stack classifier. 

.. code-block:: python

    from sklearn.model_selection import train_test_split

    # Split data into train and test sets
    df_train, df_test = train_test_split(df, test_size=0.2, random_state=42)

Specifically for BERT, the data will be split into training, validation, and test sets.

.. code-block:: python

    hf_train, hf_temp = train_test_split(df, test_size=0.3, random_state=42)
    
    # Since 10% is one-third of 30%, then test_size=2/3
    hf_val, hf_test = train_test_split(hf_temp, test_size=2/3, random_state=42)

Customizing the Dataset Format for Huggingface Model
----------------------------------------------------

Pre-trained models of Huggingface, such as BERT, have a different input format than regular 
data frames generated with the pandas library. 
Therefore, the dataset needs to be converted to a compatible format so that it can be used properly by the Huggingface model. 
This step is done so that the features of the pre-trained model can be optimized in the training and evaluation process. 

.. code-block:: python

    from datasets import Dataset as HFDataset
    hf_train_dataset = HFDataset.from_pandas(hf_train)
    hf_val_dataset = HFDataset.from_pandas(hf_val)
    hf_test_dataset = HFDataset.from_pandas(hf_test)

Customizing the Dataset Format for TextAttack
---------------------------------------------

This paper uses the TextAttack library to carry out the process of attacking the model and 
one of the materials needed to carry out the attack is the dataset to be modified. 
TextAttack also has its dataset format which is different from ordinary dataframes 
and also different from the dataset for the Huggingface model. 

.. code-block:: python
    
    from textattack.datasets import Dataset as TextAttackDataset

    # we only need the test dataset
    textattack_tuples = list(zip(test_texts, test_labels))
    textattack_dataset = TextAttackDataset(textattack_tuples)


Conclusion
----------

By applying these pre-processing steps, the dataset is prepared for the entire research scenario 
from training the machine learning models to performing attacks on the models. 
Some other common processes may not be applied as they are considered less relevant. 
Instead of improving the quality of the data, they could potentially degrade it.
