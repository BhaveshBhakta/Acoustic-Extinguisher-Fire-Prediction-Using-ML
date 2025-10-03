## Acoustic Extinguisher Fire Prediction

### Project Overview

This project aims to predict the **status of a fire being extinguished acoustically**. By analyzing a dataset of fire extinguisher parameters such as the fire's size, fuel type, distance, decibel level, airflow, and frequency, the goal is to develop a machine learning model that can accurately determine if the fire is successfully extinguished. This is a novel and interesting application in fire safety.

-----

### Technical Highlights

  * **Dataset**: A dataset named `Acoustic_Extinguisher_Fire_Dataset.xlsx`, which contains experimental data for acoustic fire extinguishing.
  * **Size**: 17,442 entries, 7 columns.
  * **Key Features**:
      * `SIZE` (of the fire), `FUEL` (type), `DISTANCE` (from extinguisher), `DESIBEL`, `AIRFLOW`, `FREQUENCY`.
  * **Approach**:
      * **Data Cleaning**: The dataset was clean with no missing values or duplicates.
      * **Exploratory Data Analysis**: Histograms, box plots, and scatter plots were used for visualization to understand data distributions and feature relationships. A `countplot` showed a balanced distribution for the target `STATUS`.
      * **Data Preprocessing**: Categorical features like `FUEL` were converted into numerical features using **One-Hot Encoding** via `pd.get_dummies`.
      * **Binary Classification**: The target variable `STATUS` indicates whether the fire was extinguished (`1`) or not (`0`).
      * **Models Used**:
          * A suite of regression models were trained, including Ridge, XGBoost, Random Forest, AdaBoost, Gradient Boosting, and Bagging. These regression models' outputs were then converted to binary classes for classification evaluation.
  * **Best Accuracy**:
      * **97.4%** with Random Forest Regressor.
      * **97.2%** with XGBoost Regressor.
      * **97.1%** with Bagging Regressor.
      * The extremely high accuracies for the ensemble models indicate that the input features are very effective at predicting fire extinction.

-----

### Purpose and Applications

  * **Acoustic Fire Extinguishing**: Enable the development of automated acoustic fire extinguishing systems.
  * **Fire Safety**: Provide a data-driven tool to optimize the parameters (decibel, frequency, etc.) of an acoustic extinguisher for maximum effectiveness.
  * **Research**: Support research in fire science and novel extinguishing technologies.
  * **Robotics**: Serve as a foundational model for a robotic fire extinguisher that can autonomously respond to fires.

-----

### Installation

Install the necessary libraries:

```bash
pip install pandas numpy seaborn matplotlib scikit-learn xgboost openpyxl
```

-----

### Collaboration

We welcome contributions to improve the project. You can help by:

  * Re-evaluating the approach of using regression models for a classification task and directly using classification models.
  * Performing comprehensive hyperparameter tuning and cross-validation for the top-performing models to ensure robustness.
  * Investigating the impact of the data preprocessing steps and trying alternative encoding methods.
  * Adding explainability (e.g., SHAP or LIME) to understand which parameters are the most critical for acoustic fire extinction.
