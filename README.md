
# 🎯 Titanic Survival Prediction - Kaggle Competition

This project is a submission for the famous [Titanic - Machine Learning from Disaster](https://www.kaggle.com/competitions/titanic) competition on Kaggle.  
The goal is to build a classification model that predicts which passengers survived the Titanic shipwreck.

## 📁 Dataset Description

The data consists of information such as:
- **Pclass** (Ticket class)
- **Sex**
- **Age**
- **SibSp** (Number of siblings/spouses aboard)
- **Parch** (Number of parents/children aboard)
- **Fare**
- **Embarked** (Port of embarkation)

The data files used:
- `train.csv` – Training set
- `test.csv` – Test set
- `gender_submission.csv` – Sample submission for test labels

## 🧹 Data Preprocessing

- Missing values in `Age` were filled using the **mean** of the column.
- Missing values in `Embarked` were filled using the **mode**.
- The test set was also filled with the **mean** of training features for simplicity.
- Categorical features `Sex` and `Embarked` were encoded using **LabelEncoder**.

## 🧠 Models Used

- ✅ **XGBoostClassifier** – Main model
- (Other models like `RandomForestClassifier` and `LogisticRegression` can be tried optionally.)

## 🧪 Evaluation

Metrics used for evaluation:
- **Accuracy**: `0.82`
- **F1-Score**: `0.73`

> Evaluation is based on the labels provided in `gender_submission.csv`.

## 🔧 Hyperparameter Tuning

Used `GridSearchCV` for hyperparameter optimization with the following grid:

```python
param_grid = {
    'max_depth': [3, 5, 7],
    'learning_rate': [0.01, 0.1, 0.2],
    'n_estimators': [100, 200, 300],
    'subsample': [0.8, 1.0],
    'colsample_bytree': [0.8, 1.0]
}
```

Tuning was done using `f1` score with **5-fold cross-validation**.

## 💡 How to Run

Make sure you have the required libraries:
```bash
pip install pandas matplotlib scikit-learn xgboost
```

Then just run the notebook in a Jupyter environment or VSCode, and you're good to go!

---

## 📌 Notes

- This project is for **educational purposes only** and is part of a Kaggle competition.
- The dataset is publicly available from Kaggle [here](https://www.kaggle.com/competitions/titanic).
- You can improve the results by performing deeper feature engineering and using ensemble models.
