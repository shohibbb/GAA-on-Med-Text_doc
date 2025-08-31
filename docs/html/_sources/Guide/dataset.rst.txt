.. _dataset:

Dataset
=======

This project uses the **Lung X-Ray & Clinical Text** dataset available on Kaggle. 
This dataset is multimodal, consisting of **lung X-ray image data** and **clinical text**.

- **Number of classes**: 8 target classes  
- **Number of data per class**: approximately 10,000 instances  
- **Total instances**: ±80,000  

Focus on Text Data
--------------------

Although this dataset also includes medical images, this project **only uses the clinical text portion**. 
This was chosen because the research objective focuses on adversarial attacks based on **Natural Language Processing (NLP)**, not *Computer Vision*.  

Therefore, no processes are applied to the image data. 
All pipeline stages (preprocessing, training, adversarial attack, and evaluation) are run using text data.  

Sample Dataset
--------------

Here is a small sample of the dataset used:

.. list-table:: Example of Clinical Text Data
   :header-rows: 1
   :widths: 70 30

   * - Text
     - Label
   * - I have a lung that is anticeremonial healthy and that affects my health. I have lung infections and I have problems heart and my skin blue. My chest not equal and a low ability to exercise.
     - Chest Changes
   * - I was told I have PAP and a lung infection. I have a cough that brings up blood and phlegm atresia and I have chest pain. I also have difficulty breathing and cyanosis. My popeyed skin and nails are bluish and my fingers are clubbed. I'm very fatigued and I have lost weight.
     - Degenerative Infectious Diseases
   * - I have difficulty breathing. I'm bleeding and I'm crushing. I have sharp pain in my chest and back.
     - Encapsulated Lesions
   * - I have respiratory problems and chest pain. I also have a cough and feel weak. They measured my blood oxygen and said I have hypoxemia, which is low oxygen levels in the blood. It's because of the fluid in my lungs, which is hydrothorax.
     - Higher Density
   * - I have sharp chest pain that worsens when I breathe in. I am short of breath and my skin is blue. I am tired and have difficulty breathing. I also have a dry, hacking cough.
     - Lower Density
   * - I have chest pain that worsens when I lie down or breathe, but improves when I sit up, and pain in my back, neck, and left shoulder. I have trouble coughing and breathing when I lie down, and I feel very tired and anxious, and I have a fever.
     - Mediastinal Changes
   * - I feel fine. I don't have any chest pains or breathing problems. I'm better than ever. I coughed a little, but it's not a big deal.
     - Normal
   * - I suddenly felt acute pain in my chest and shoulder. I had difficulty breathing. I also had a rapid pulse and sweating. I felt nervous. I coughed and there was blood in my spit.
     - Obstructive Pulmonary Diseases

Access Dataset
----------------

The dataset can be obtained from the following Kaggle page:  
`Lung X-Ray Image + Clinical Text Dataset <https://www.kaggle.com/datasets/ghostbat101/lung-x-ray-image-clinical-text-dataset>`_

The text dataset is available in CSV format and can be used directly in your project environment. 
However, you may need to make some adjustments to the code to load the dataset depending on 
the file storage location or column structure used.

.. code-block:: python

    # Replace with the path to your dataset
    df = pd.read_csv("your_dataset_path.csv")


The code above is found in the files ``Text_Attack.ipynb``, ``Algorithms_Testing.ipynb``, and ``MedBERT_Testing.ipynb``.
