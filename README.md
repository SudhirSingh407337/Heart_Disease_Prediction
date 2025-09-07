# 🫀 Heart Disease Prediction

## 📌 Project Overview
This project focuses on **predicting heart disease risk** using advanced feature engineering techniques and machine learning models.

- 🔍 **Comprehensive Data Analysis** – exploring relationships between medical indicators and heart disease
- 🛠 **Feature Engineering** – implementing feature binning, scaling, and interaction terms
- 📊 **Feature Transformation** – standardizing numerical features and creating categorical bins
- 🤖 **Predictive Modeling** – comparing Logistic Regression and Random Forest models
- 🎯 **Goal** – identify key risk factors and build accurate prediction models for heart disease detection

## Dataset

The dataset contains medical records with the following features:

- **Age**: Age of the patient in years
- **Sex**: Gender of the patient
- **ChestPainType**: Type of chest pain experienced
- **RestingBP**: Resting blood pressure in mm Hg
- **Cholesterol**: Serum cholesterol in mg/dl
- **FastingBS**: Fasting blood sugar > 120 mg/dl (1 = true; 0 = false)
- **RestingECG**: Resting electrocardiogram results
- **MaxHR**: Maximum heart rate achieved
- **ExerciseAngina**: Exercise-induced angina (1 = yes; 0 = no)
- **Oldpeak**: ST depression induced by exercise relative to rest
- **ST_Slope**: Slope of the peak exercise ST segment
- **HeartDisease**: Heart disease diagnosis (1 = present; 0 = absent) - target variable

---

## Key Techniques Implemented

### 1. Data Exploration & Visualization
  - Statistical summary of patient attributes
  - Distribution analysis of target variable (heart disease cases)
  - Visualization of continuous variables by heart disease status
  - Correlation analysis between numerical features
  - Identification of key relationships with heart disease risk

### 2. Feature Binning
  - Three binning approaches for continuous variables:
    - Manual binning based on medical domain knowledge
    - Equal-width binning for uniform intervals
    - Equal-frequency (quantile) binning for balanced distribution
  - Age binned into meaningful categories: Young Adult, Middle-Aged, Senior, Elderly
  - Cholesterol binned according to clinical thresholds: Desirable, Borderline, High
  - One-hot encoding of categorical bins to capture non-linear relationships

### 3. Feature Scaling & Standardization
  - Standardization of numerical features using `StandardScaler`
  - Normalization of features to zero mean and unit variance
  - Improved convergence for distance-sensitive algorithms
  - Equal contribution of features regardless of original units
  - Visualization of distributions before and after scaling

### 4. Interaction Terms Creation
  - Generation of interaction features using `PolynomialFeatures`
  - Creation of pair-wise interactions between standardized features
  - Capture of combined effects between medical indicators
  - Identification of top interaction terms by correlation with heart disease
  - Visualization of most significant interaction features

### 5. Model Training & Evaluation
  - Creation of multiple feature sets for comparison:
    - Original features
    - Original + Scaled features
    - Original + Binned features
    - Original + Interaction terms
    - All features combined
  - Training and evaluation of:
    - Logistic Regression classifier
    - Random Forest classifier
  - Comprehensive performance metrics:
    - Accuracy, precision, recall, F1-score, and AUC
    - Detailed classification reports
    - Comparison across all feature engineering approaches

---

## Results

The models achieved varying performance metrics depending on the feature engineering approach:

- Feature binning captured non-linear relationships, especially in age and cholesterol
- Standardization improved model convergence for logistic regression
- Interaction terms revealed important combined effects between features
- The best performing model combined multiple feature engineering techniques
- Both algorithms showed strong predictive capability, with Random Forest typically providing the highest accuracy

Key findings include:
- ST_Slope, ExerciseAngina, and MaxHR were among the most important predictors
- Several interaction terms between Age, MaxHR, and other features showed strong predictive power
- Binning continuous variables helped capture threshold effects in risk factors
- Feature engineering significantly improved model performance compared to using only original features

---

## Requirements
- Python 3
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

---

## How to Use
1. Clone this repository
2. Ensure you have all required packages installed
3. Open the Jupyter notebook `Heart_Disease_Prediction.ipynb`
4. Run the cells sequentially to see the analysis and results

---

## File Structure
- `Heart_Disease_Prediction.ipynb` - The main Jupyter notebook containing all analysis and code
- `heart.csv` - Dataset with heart disease information
- `README.md` - This file with project information

---

## Key Insights
- Feature engineering techniques significantly improved predictive power
- The interaction between age and maximum heart rate suggests that the impact of heart rate on heart disease risk varies across age groups
- Cholesterol levels demonstrate a non-linear relationship with heart disease risk, with specific thresholds being more clinically relevant than continuous values
- Standardization is particularly important for logistic regression performance
- Feature binning helps capture threshold effects common in medical diagnoses
- Interaction terms reveal how combined factors can amplify risk in ways not captured by individual features
