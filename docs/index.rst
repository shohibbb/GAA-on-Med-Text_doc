.. Exploiting Vulnerabilities of Machine Learning Models on Medical Text via Generative Adversarial Attacks documentation master file, created by
   sphinx-quickstart on Thu Aug 21 10:43:36 2025.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Exploiting Vulnerabilities of Machine Learning Models on Medical Text via Generative Adversarial Attacks
========================================================================================================
**Exploiting Vulnerabilities of Machine Learning Models on Medical Texts 
via Generative Adversarial Attacks** is a research project designed to 
evaluate the resilience of machine learning models in the field of healthcare. 
This project focuses on evaluating several machine learning models and 
transformer-based models used in text classification tasks. 
It is designed to provide insights into the vulnerabilities of AI models 
currently widely used in the medical and healthcare fields. 
The project still has limitations related to data, and we hope to apply it 
to more complex text data in the future.

GitHub: `https://github.com/shohibbb/Exploiting-Vulnerabilities-of-Machine-Learning-Models <https://github.com/shohibbb/Exploiting-Vulnerabilities-of-Machine-Learning-Models>`_

At its core, this project utilizes adversarial attack architecture, namely a re-implementation of TextFooler from TextAttack, which highlights the vulnerabilities of medical NLP models.
The algorithm crafts perturbations in medical text, while the discriminator ensures linguistic and semantic plausibility. 
This process allows researchers to explore security risks in clinical AI systems, while encouraging the development of robust countermeasures.  
By design, the framework helps stakeholders understand how small textual changes can impact prediction reliability without compromising overall clinical readability.

.. toctree::
   :maxdepth: 1
   :caption: User Guide:

   Guide/overview
   Guide/dataset
   Guide/result 
   Guide/future_research

.. toctree::
   :maxdepth: 1
   :caption: Content

   Content/preprocessing
   Content/EDA
   Content/models
   Attack Algorithm<Content/attack_algorithm>
   Content/eval

