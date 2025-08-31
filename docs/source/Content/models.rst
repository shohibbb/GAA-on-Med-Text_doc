Classification Models
=====================

This section describes the classification models used in this study. 
In total, five traditional machine learning models, one ensemble model, 
and one transformer-based model were applied. 
Given that the data used in this project is text data, building a machine learning model with traditional algorithms requires word representation techniques.  

In this project, three word representation techniques were used, i.e.

- Word2Vec
- Global Vector(GloVe)
- FastText

The five traditional models used in this project are:

1. Logistic Regression
2. Support Vector Machine
3. Naive Bayes
4. Random Forest
5. Extreme Gradient Boosting

For the ensemble model, this project uses the stacking classifier concept, which combines three traditional models with the best average accuracy as base learners. Thus, the stacking classifier used consists of:

- Random Forest
- Extreme Gradient Boosting
- Support Vector Machine

then the best model will be used as a meta learner, namely

- Random Forest

The transformer-based model used in this project is *MedBERT*. MedBERT was chosen based on the fact that this project involves an NLP task in the form of text classification with a dataset theme in the form of medical data. Since MedBERT is a transformer-based model specifically designed for text classification in the medical domain, the use of additional word representation techniques is no longer necessary.

The implementation details and full source code for each model 
are provided in the project repository. 
You can directly access the corresponding Jupyter Notebooks here:

- `algorithms_testing.ipynb <https://github.com/shohibbb/Exploiting-Vulnerabilities-of-Machine-Learning-Models/blob/main/Algorithms_Testing.ipynb>`_  
  (contains the implementation of traditional and ensemble models)

- `MedBERT_testing.ipynb <https://github.com/shohibbb/Exploiting-Vulnerabilities-of-Machine-Learning-Models/blob/main/MedBERT_Testing.ipynb>`_  
  (contains the implementation of the transformer-based model)

.. note::
   In this documentation, we only provide the conceptual explanation of 
   the models. Please refer to the linked notebooks for the full code 
   implementation and experimental details.
