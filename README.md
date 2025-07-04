

# Task A - Gender Classification 

## Overview

This task involved classifying whether a person is male/female  based on a provided image  dataset. The dataset was split into training and validation sets, with a notable class imbalance.

## Approach

* **Data Handling:**

  * Detected class imbalance in the training data.
  * Applied upsampling to the minority class after feature extraction to balance the distribution.

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

** Just run the jpynb file with the correct paths

---

# Task B - Face Recognition 

## 📌 Objective

The goal was to perform **face recognition** using deep learning techniques that can learn discriminative face embeddings.

---

## 🧠 Approach

* **Loss Function:**
  Used **Triplet Loss** to train the network to bring embeddings of the same identity closer and push different ones apart.

* **Embedding Model:**
  Employed **MobileNetV2** (with `pooling='avg'` and no classification head) to extract 128-dimensional face embeddings.

* **Triplet Generator:**
  Built a custom generator that dynamically creates triplets:
  **(Anchor, Positive, Negative)** —
  where anchor and positive are images of the same person, and negative is of a different person.

* **Siamese Network:**
  Constructed a model that processes the three images through a **shared embedding network**, then applies triplet loss.

* **Training:**
  Trained for **10 epochs** using `Adam` optimizer with learning rate `0.0001`.

---

## 📊 Evaluation

Evaluated on the validation set using cosine similarity between embeddings.

* **Top-1 Accuracy:** **98.25%**
* **F1 Score:** **0.9826**

---

## 💾 Output

* Saved the trained embedding model (`face_embedding_model.h5`) for use in inference and verification tasks.

** First run the preprocessing code.
** Then take the preprocessed folders and run the training and testing codes.

