[Project on Kaggle](https://www.kaggle.com/code/ahmedmoneimm/pr-assign-2)

# Skin Cancer Classification and Segmentation

This project tackles multiclass classification and segmentation tasks using the HAM10000 dataset. It focuses on two main objectives:

- **Classification:** Identify skin lesion types from images.
- **Segmentation:** Delineate lesion boundaries in the images.

The skin lesion classes include:
- **MEL:** Melanoma
- **NV:** Melanocytic nevi
- **BCC:** Basal cell carcinoma
- **AKIEC:** Actinic keratoses and intraepithelial carcinoma
- **BKL:** Benign keratosis-like lesions
- **DF:** Dermatofibroma
- **VASC:** Vascular lesions

---

## Data Loading and Splitting (20 points)
- **Dataset Source:** Available on Kaggle (includes two folders and one CSV file with labels).
- **Contents:**
  - **Images Folder:** Contains skin lesion images.
  - **Masks Folder:** Contains segmentation masks.
  - **Labels File:** Provides image labels.
- **Data Challenges:**
  - **Bias:** There is significant class imbalance, resulting in bias across the lesion classes.
  - **Data Leakage:** We identified duplicated data (with different names) using pHash, which could lead to data leakage if not handled properly.
- **Note:** The dataset is not pre-split; therefore, it has been divided into training, validation, and test sets as part of this project.

---

## Classification Model (30 points)
- **Approach:** Implemented a Convolutional Neural Network (CNN) in PyTorch.
- **Constraints:** The model contains fewer than 60 million parameters.
- **Evaluation Metrics:**
  - **Total Parameters:** Detailed results available in the notebook.
  - **Overall Accuracy:** Detailed results available in the notebook.
  - **Confusion Matrix:** Detailed results available in the notebook.
  - **Per-Class Metrics:** Precision, Recall, and F1 Score for each class are computed.

---

## Segmentation Model (30 points)
- **Approach:** Developed a segmentation model using an appropriate PyTorch architecture - used Resnet34 as backbone and created a classification head and a segmentation head.
- **Training:** The model is trained on the training set and validated on the validation set.
- **Evaluation Metrics:**
  - **Mean Dice Score: 0.8543**
  - **Mean IoU: 0.7084**

---

## Evaluation and Report (20 points)
A comprehensive report is provided which summarizes:
- The overall approach and model architectures.
- Hyperparameters and training processes.
- Detailed evaluation results with visualizations including:
  - Loss and accuracy curves.
  - Confusion matrices.
  - Example segmentation outputs.
- Insights into challenges faced (including data bias and leakage due to duplicate data identified via pHash) and the strategies used to address them.

---

## Bonus Tasks
- **Bonus 1 (10 points): Data Leakage Report**
  - Identification and analysis of data leakage due to duplicated data with different names (detected using pHash).
  - Impact assessment and mitigation strategies, supported by visual representations.
  
- **Bonus 2 (10 points): Unified Model Approach**
  - Implementation of a single model with two distinct final layers (one for classification and one for segmentation) to share common weights, reducing memory usage.
