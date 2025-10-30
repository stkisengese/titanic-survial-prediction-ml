# Titanic Survival Prediction

This project predicts whether a passenger on the Titanic survived or not. It's a classic machine learning project based on the Kaggle competition of the same name. This implementation achieves an accuracy of over 80%.

## Dataset

The dataset is from the Kaggle Titanic competition. You can find the data in the `data/` directory:
- `train.csv`: Training data
- `test.csv`: Test data
- `gender_submission.csv`: Example submission file

## Features

The model uses the following features:
- `Pclass`: Passenger class
- `Sex`: Gender of the passenger
- `Age`: Age of the passenger
- `Fare`: Fare paid by the passenger
- `Embarked`: Port of embarkation
- `Title`: Title of the passenger (e.g., Mr, Mrs, Miss)
- `FamilySize`: The total number of family members on board
- `IsAlone`: A boolean indicating if the passenger was traveling alone
- `AgeGroup`: Age grouped into bins
- `FareBin`: Fare grouped into bins
- `FarePerPerson`: Fare per person in the family
- `Deck`: The deck the passenger was on

## Model

The project uses a Logistic Regression model. The notebook `notebook/main.ipynb` explores other models like Random Forest and Gradient Boosting, but the final selected model is Logistic Regression due to its good balance of performance and generalization.

## Installation

To run this project, you need to have Python 3 and pip installed. Then, you can install the required dependencies from `requirements.txt`:

```bash
pip install -r requirements.txt
```

## Usage

The main code is in the Jupyter Notebook `notebook/main.ipynb`. To run it, you can start the Jupyter Notebook server:

```bash
jupyter notebook
```

Then, open `notebook/main.ipynb` in your browser.

## Author

- **Username:** skisenge01edukisumu

## Iterations

### Iteration 1: Naive Baseline
- **Assumption:** All passengers died.
- **Kaggle Score:** 0.6220
- **Learning:** Establishes a baseline score to beat. Any model performing worse than this is not useful.

### Iteration 2: Logistic Regression with Basic Features
- **Features:** `Pclass`, `Sex`, `Age`, `Fare`, `SibSp`, `Parch`.
- **Preprocessing:** Filled missing values and encoded categorical features.
- **Validation Accuracy:** ~78.5% (5-Fold Cross-Validation)
- **Kaggle Score:** 0.75358
- **Learning:** A simple Logistic Regression model with basic feature cleaning already provides a significant improvement over the naive baseline. This shows the importance of using relevant features.

### Iteration 3: Smart Feature Engineering
- **New Features:** `FamilySize`, `IsAlone`, `Title`, `AgeGroup`, `FareBin`, `FarePerPerson`, `Deck`.
- **Model Comparison:** Compared Logistic Regression with Random Forest.
- **Validation Accuracy:** 
    - Logistic Regression: ~81.5% CV
    - Random Forest: ~83.8% CV
- **Learning:** Feature engineering is crucial. Creating new features that capture more information (like `FamilySize` or `Title`) can lead to a noticeable improvement in model performance. The Random Forest model performed better than Logistic Regression, suggesting that a more complex model can capture non-linear relationships in the data.

### Iteration 4: Model Optimization & Hyperparameter Tuning
- **Approach:** Compared multiple models (Logistic Regression, Random Forest, Gradient Boosting, SVM, KNN) and tuned hyperparameters for the top performers.
- **Model Performance:**
    - **Gradient Boosting:** ~83.2% CV (Best baseline)
    - **Random Forest:** ~83.5% CV (After tuning)
    - **Logistic Regression:** ~81.1% CV (After tuning)
- **Final Model Selection:** **Logistic Regression**.
- **Learning:** While more complex models like Gradient Boosting and Random Forest achieved slightly higher cross-validation scores, they also showed signs of overfitting (a significant gap between training and validation accuracy). The simpler Logistic Regression model, although slightly less accurate, demonstrated better generalization. This highlights a critical trade-off in machine learning: the balance between performance and generalization. For this project, a simpler, more robust model was chosen as the "safest" option.