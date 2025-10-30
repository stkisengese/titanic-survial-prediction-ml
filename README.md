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

### Iteration 1: Logistic Regression
- Assumption: All people died
- Kaggle Score: 0.6220
- Learning: Simple preprocessing already beats the baseline.

### Iteration 2: Logistic Regression
- Features: Pclass, Sex, Age, Fare, SibSp, Parch
- Preprocessing: filled missing values, encoded categories
- Validation Accuracy: 0.78
- Kaggle Score: 0.75358
- Learning: Simple preprocessing already beats the baseline.

### Iteration 3: Feature Engineering
- New Features: FamilySize, IsAlone, Title, FareBin, FarePerPerson, AgeGroup, Deck
- Preprocessing: filled missing values, encoded categories
- Validation Accuracy: 0.8171
- Kaggle Score: 0.75358
- Learning: RandomForest model does better than Logistic regression model
