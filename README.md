Model Backend for 2026 BDA Student Completion Prediction Challenge
============================================
Summary
----------------
### We placed 15th at private LB.

This repository contains **the final version of code and models for submission** used for the 2026 BDA Student Completion Prediction Challenge hosted on DACON. ([Competition Link](https://dacon.io/competitions/official/236664))

Team Information
----------------
- **Team Name: Placeholder**
- **Public rank: 12th**
- **Private rank: 15th**
- **Private score: 0.41626**
- **Team Members: knowin_kyeong (Team Leader), William Han, 긴카호, 코나치**

Directory Structure
-------------------
The base directory follows this directory structure (Simplified):

*Note: **In colab environment, you have to upload '2026PredictingBDACompletion'** on your Google Drive.*

*Note 2: **We removed /data files due to potential risks of violating DACON's data sharing policies.** Please replace it with your own copy of the dataset downloaded from DACON website.*

```
2026PredictingBDACompletion
│  requirements.txt
│  submission_final.csv
│
├─data (Place your own copy of dataset here)
│      sample_submission.csv
│      test.csv
│      train.csv
│
├─outputs
│      submission_catboost.csv
│      submission_xgboost.csv
│
└─src
       001_xgboost.ipynb
       002_catboost.ipynb
       003_hard_AND_ensemble.ipynb
```
**submission_final.csv** is the final submission file.

How to Run
----------
1. Place the 2026PredictingBDACompletion directory in your colab environment.
2. Set up the dataset in the **/data** directory from DACON website.
3. Run **all notebooks(001_xgboost, 002_catboost)** in the **/src** directory to train models and save the results in the **/outputs** directory.
4. Run **003_hard_AND_ensemble** in the **/src** directory to generate final submission file, which will be saved as **submission_final.csv** in the base directory.
5. Submit the final submission file from **submission_final.csv** to DACON!

Requirements
------------
- All required python package is listed in **requirements.txt**.
- You need **GPU environment** to run the training notebooks.
- We tested only on **Google Colab Pro+, Tesla T4 GPU** environment. It may not work on other environments. Therefore **even though executing pip command with requirements.txt, some packages in the default colab environments is absent or have different versions, which may cause errors**. You can try to install missing packages **manually**.

Models Included
---------------
- **XGBoost**: A model using XGBoost to deal numerical features mainly.
- **CatBoost**: A model using CatBoost to deal categorical features mainly.

Reproducibility
-----------------
- All random seeds are fixed for reproducibility.
- **However, according to the Catboost documentation, exact bit-level reproducibility may not be guaranteed when using GPU training.**
- Therefore, We assume that **our results may vary slightly in different environments**, so we also provide the pretrained model weights for your reference. You can use the pretrained model weights to simulate our LB score results with setting **MODE=Load** in the training notebooks.
- **We observed that the final private LB score may vary by about ±0.0005 (equivalent with 1~2 indices-level difference) depending on the environment.**

Contact
-------
If you have any questions, **please create an issue in this repository** or contact the team leader, knowin_kyeong, **via email at juwon0718@snu.ac.kr.**

Release
---------------
We released this repository to public. (2026-02-24)


