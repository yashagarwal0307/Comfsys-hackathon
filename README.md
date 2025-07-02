

# Task A - Gender Classification 

## Overview

This task involved classifying gender based on a provided dataset. The dataset was split into training and validation sets, with a notable class imbalance.

## Approach

* **Data Handling:**

  * Detected class imbalance in the training data.
  * Applied upsampling to the minority class to balance the distribution.

* **Feature Extraction:**

  * Used **EfficientNet-B3 (EffNetB3)** as a feature extractor.
  * Normalized extracted features before feeding them into classifiers.

* **Modeling:**

  * Implemented a **Voting Classifier** combining:

    * Random Forest
    * XGBoost
    * CatBoost
  * Each model contributed equally, with a final classification threshold set at **0.5**.

## Results

* **Best validation accuracy:** **93.8%**

---

Let me know if you want this expanded with setup instructions, code usage, or visualizations.
