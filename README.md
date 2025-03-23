# LightGBM-Clean-Train-Eval

This project demonstrates a complete pipeline for data preprocessing and model training using LightGBM. It includes loading, cleaning, imputing, and preparing both training and evaluation datasets, followed by model training and prediction.

## 🚀 Features

- Data cleaning (handles `"Boom!"`, `"F"`, `"?"` as missing values)
- Imputation of:
  - Numerical columns using mean
  - Categorical columns using most frequent value
- Outlier capping based on IQR
- Model training with LightGBM
- Exporting cleaned data and trained model

## 📁 Files

- `train.ipynb`: Jupyter notebook containing all preprocessing and training steps
- `TrainOnMe.csv`: Raw training dataset
- `EvaluateOnMe.csv`: Raw evaluation dataset
- `TrainOnMe_Cleaned.csv`: Cleaned training data
- `EvaluateOnMe_Cleaned.csv`: Cleaned evaluation data
- `model.joblib`: (Optional) Saved trained model

## 🔧 Steps Performed

1. **Load Data**
   - Read CSV files using pandas
   - Drop unnecessary index columns like `"Unnamed: 0"`

2. **Clean & Preprocess**
   - Replace placeholders like `"Boom!"`, `"F"`, and `"?"` with `NaN`
   - Convert columns to proper numeric/object types
   - Impute missing values:
     - Numeric: mean strategy
     - Categorical: most frequent strategy

3. **Outlier Handling**
   - Use IQR method to cap outliers in all numeric columns

4. **Model Training**
   - Train a LightGBM model using the cleaned data
   - Save the model using `joblib` (if applicable)

5. **Output**
   - Save cleaned datasets as CSV
   - Export model (optional)

## 📦 Requirements

```bash
pip install pandas numpy lightgbm scikit-learn joblib
```

Alternatively:

```bash
pip install -r requirements.txt
```

## 📝 Notes

- The same preprocessing logic is applied to both training and evaluation datasets
- Outlier capping improves generalization performance
- Easily extendable to other datasets or models

