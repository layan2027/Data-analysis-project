Naive Bayes Classifier for Titanic Dataset

Overview
This project implements a Naive Bayes Classifier on the Titanic dataset to classify passengers based on their embarkation points. 
The project involves data preprocessing, feature engineering, model training, evaluation, and data visualization to gain insights into the dataset and assess model performance.

Dataset
The dataset used in this project contains details of passengers on the Titanic. Key columns in the dataset include:

- `PassengerId`: Unique identifier for each passenger.
- `Pclass`: Passenger class (1st, 2nd, or 3rd).
- `Name`: Full name of the passenger.
- `Sex`: Gender of the passenger.
- `Age`: Age of the passenger.
- `SibSp`: Number of siblings or spouses aboard.
- `Parch`: Number of parents or children aboard.
- `Ticket`: Ticket number.
- `Fare`: Price of the ticket.
- `Cabin`: Cabin number (if available).
- `Embarked`: Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton).

Dataset Path
Ensure the dataset is available at `test.csv`.

Project Steps

1. Data Preprocessing
- Handling Missing Values: Filled missing values in `Age` and `Fare` with the median and in `Embarked` with the mode.
- Label Encoding: Converted categorical variables, such as `Sex` and `Embarked`, into numerical values to enable model training.

2. Feature Engineering
Selected relevant features for classification:
- Features: `Pclass`, `Sex`, `Age`, `SibSp`, `Parch`, `Fare`
- Target: `Embarked` (encoded to numerical values)

3. Model Implementation: Naive Bayes Classifier
A Naive Bayes classifier was chosen for classification. This model operates based on Bayes' Theorem and assumes conditional independence between features.

- Model: `MultinomialNB` from the `scikit-learn` library.
- Training-Testing Split: The dataset is split 70-30 for training and testing.

4. Evaluation Metrics
The model’s performance is evaluated using:
- Accuracy Score: Measures overall correct predictions.
- Confusion Matrix: Displays true versus predicted labels.
- Classification Report: Includes precision, recall, and F1-score for each embarkation class.

5. Data Visualization
Visualizations created to better understand the dataset:
- Age Distribution: Histogram displaying age distribution of passengers.
- Fare Distribution: Histogram showing fare distribution.
- Passenger Count by Embarkation Port: Count plot of passengers per embarkation port.
- Correlation Matrix: Heatmap showing correlations among numerical features.

6. Model Training and Prediction
The Naive Bayes classifier was trained on the processed dataset, followed by predictions on the test set and evaluation based on the selected metrics.

Getting Started

Requirements
- Python 3.x
- Libraries: `pandas`, `scikit-learn`, `matplotlib`, `seaborn`, `joblib`

Installation
To install the required libraries, use the following command:

pip install pandas scikit-learn matplotlib seaborn joblib


Running the Project
1. Clone the repository or download the project files.
2. Run the notebook or script in your preferred environment (e.g., Jupyter Notebook).
3. Ensure the dataset path is correctly set to `test.csv`.
4. Execute the cells to complete data preprocessing, model training, evaluation, and visualizations.

Saving the Model
The trained Naive Bayes model is saved as a `.pkl` file for future use:

import joblib
joblib.dump(nb_classifier, 'naive_bayes_classifier_model.pkl')


Results
After running the project, outputs include:

- Accuracy Score: Printed in the output.
- Confusion Matrix: Displayed as a matrix.
- Classification Report: A detailed report with precision, recall, and F1-score for each class.

Visualization Examples
Generated visualizations include:
- Age and Fare Distributions
- Passenger Count by Embarkation Port
- Correlation Matrix Heatmap

Notes
- Data preprocessing is essential to handle missing values and categorical encoding.
- The Naive Bayes classifier, while simple, provides useful classification insights on this dataset.
- Class imbalance in embarkation points may affect model accuracy for minority classes.

License
This project is licensed under the MIT License.