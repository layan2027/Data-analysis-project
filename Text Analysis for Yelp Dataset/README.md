Yelp review classification

Overview
This project analyzes Yelp business data to predict star ratings based on business categories using a logistic regression model. The dataset is large, so a 10% random sample is used to make it manageable. The analysis includes data preprocessing, model training, evaluation, and visualization of the model's performance.

Dataset
The dataset used in this project is a large Yelp dataset containing information about businesses. Key columns include:

business_id: Unique identifier for each business.
name: Business name.
categories: Categories describing the type of business.
stars: Average rating of the business (target variable).
review_count: Number of reviews received by the business.

Dataset Path
The dataset file should be located at /kaggle/input/yelp-dataset/yelp_academic_dataset_business.json.

Project Steps
1. Import Libraries
Required libraries are imported to handle data processing, model training, evaluation, and visualization.

2. Load a 10% Sample of the Dataset
Since the dataset is too large, it is loaded in chunks. A 10% random sample is taken from each chunk and concatenated to create a smaller, more manageable dataset.

3. Data Overview and Initial Visualizations
The distribution of business ratings is visualized to understand the class balance of star ratings across businesses.

4. Text Preprocessing
Text data in the categories column is preprocessed:
Lowercasing: Converts all text to lowercase.
Removing non-alphabetic characters: Keeps only letters and spaces, removing punctuation and numbers.

5. Split the Dataset
The data is split into training and testing sets, with the categories column used as features and stars ratings as the target variable. The stars column is rounded and converted to integer to ensure compatibility with the classifier.

6. Vectorization
A TF-IDF vectorizer is applied to convert the cleaned categories text data into numerical features for model training.

7. Train the Model
A logistic regression model is trained on the transformed training data.

8. Make Predictions
The trained model is used to predict star ratings on the test set.

9. Evaluate the Model
Model performance is evaluated using:
Accuracy Score: Shows the overall prediction accuracy.
Classification Report: Displays precision, recall, and F1-scores for each star rating, with zero_division=1 to handle undefined metrics.
Class Distribution Check: Compares the distribution of actual versus predicted labels.

10. Visualization of Model Performance
A confusion matrix heatmap visualizes the model’s performance in predicting each star rating.

Getting Started
Requirements
Python 3.x
Libraries: pandas, matplotlib, seaborn, sklearn
Installation
To install the required libraries, use the following command:

pip install pandas matplotlib seaborn scikit-learn

Running the Project
Clone the repository or download the project files.
Place the dataset in the project directory.
Run the code in a Kaggle notebook or Jupyter environment.

Results
The outputs of this project include:
Accuracy Score: Printed as the overall accuracy of the model.
Classification Report: Detailed report with precision, recall, and F1-scores for each rating category.
Class Distribution: Distribution of actual and predicted ratings to check for class balance.
Confusion Matrix: Heatmap displaying correct and incorrect predictions across star ratings.

Insights Gained
Category Influence: Certain business categories are influential in predicting star ratings, though performance may vary based on class balance.
Class Imbalance: If star ratings are unevenly distributed, some ratings may have limited representation in predictions.

Notes
The model’s accuracy and F1-scores may be affected by class imbalance, especially if certain star ratings are underrepresented in the dataset.
Adjusting thresholds for sampling or adding other text columns could improve the model.

License
This project is licensed under the MIT License.