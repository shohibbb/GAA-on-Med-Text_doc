.. _evaluation:

Evaluation Process
==================

Model Evaluation
------------------
The built model will be evaluated using accuracy, precision, recall, and F1-score metrics. These four metrics provide a comprehensive overview of the model's performance in recognizing medical text. Accuracy shows how many predictions are correct, precision measures the accuracy of positive predictions, recall assesses the model's ability to capture all relevant cases, while F1-score balances the results of precision and recall. In addition, prediction errors are also noted to identify patterns of weakness in the model, which can serve as a basis for future performance improvements. 

Model performance measurement is simplified by the functions provided by the *scikit-learn* library.
However, to provide a clearer understanding, the mathematical formulation of the metrics used is presented below.

**Formulasi Metrik:**

- **Accuracy**

  .. math::

     Accuracy = \frac{TP + TN}{TP + TN + FP + FN}

- **Precision**

  .. math::

     Precision = \frac{TP}{TP + FP}

- **Recall**

  .. math::

     Recall = \frac{TP}{TP + FN}

- **F1-Score**

  .. math::

     F1 = 2 \cdot \frac{Precision \cdot Recall}{Precision + Recall}

**Keterangan:**

- **TP (True Positive):** Positive cases that are correctly predicted as positive.  
- **TN (True Negative):** Negative cases that are correctly predicted as negative.  
- **FP (False Positive):** Negative cases that are incorrectly predicted as positive.
- **FN (False Negative):** Positive cases that are incorrectly predicted as negative. 


Attack Evaluation
-----------------

Attack evaluation is the final stage of this research. Two main metrics are used, namely *Attack Success Rate* and *Accuracy After Attack*.  
- **Attack Success Rate** shows how often adversarial examples succeed in causing the victim model to make incorrect predictions. This metric helps analyze the effectiveness of the attack algorithm and the quality of the generated adversarial examples.  
- **Accuracy After Attack** is used to determine the model's vulnerability level. This value is calculated by comparing the initial accuracy before the attack with the accuracy after the attack.

The results of these two metrics provide a comprehensive picture of the model's vulnerability to adversarial attacks and serve as a basis for future model improvements to make it more resilient to attack risks.

In addition, the evaluation also covers three categories of adversarial examples: **successful**, **failed**, and **skipped**.

- In *successful examples*, analysis is performed on changes in words, grammar, and similarities to the source text. Similarity is measured using cosine similarity, a popular technique for comparing two objects.  
- In failed examples, the evaluation focuses on the algorithm and data to understand the cause of the attack failure.  
- In skipped examples, the reasons why no modifications were made or why the algorithm was unable to continue further analysis are examined.  

