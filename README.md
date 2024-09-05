Explanation of the Two Files:
1. dissertation_code.ipynb:
This Jupyter notebook file is primarily used for:
•	Data Preprocessing: Cleaning and preparing the dataset for analysis.
•	Model Training: Developing machine learning models, selecting the best model, and tuning it.
•	Model Evaluation: Testing and comparing different models for accuracy, precision, recall, and other performance metrics.
•	Final Model Selection: Choosing the best performing model (in this case, a stacking classifier).
•	Saving the Model: Once the best model is identified, it is saved (often as a pickle file) for later use in deployment.
Here's a breakdown of the key steps likely performed in dissertation_code.ipynb:
1.	Loading the Dataset:
o	The credit card fraud dataset is loaded (probably using Pandas).
2.	Data Preprocessing:
o	Missing values handling.
o	Feature engineering (e.g., creating new features or transforming existing ones).
o	Feature scaling (e.g., using StandardScaler or MinMaxScaler).
o	Data splitting into training and test sets.
3.	Model Development:
o	Multiple machine learning models are trained and compared (e.g., Random Forest, XGBoost, Gradient Boosting and Stacking.).
o	Hyperparameter tuning ( RandomizedSearchCV) is likely applied to fine-tune the models.
4.	Model Selection:
o	Models are evaluated using metrics such as accuracy, precision, recall, F1-score, and ROC AUC score.
o	The Stacking Classifier (an ensemble method that combines multiple models) is chosen as the best performing model.
5.	Model Testing:
o	The selected model is tested on the holdout test set to ensure its performance generalizes well to unseen data.
o	Model performance is analysed using confusion matrices, classification reports, and ROC curves.
6.	Model Saving:
o	The final trained stacking classifier is saved to a file (using pickle or joblib) to be deployed later in the web app.
 
2. app (1).py:
This Python script is a Streamlit app used to deploy the best model (Stacking Classifier) as a web-based application for Credit Card Fraud Detection.
Key Components in app (1).py:
1.	Streamlit Setup:
o	The file starts by importing the required libraries (Streamlit, NumPy, Pandas, and possibly other libraries like pickle for loading the saved model).
o	Streamlit is used to create a simple and interactive web interface.
2.	Loading the Best Model:
o	The saved Stacking Classifier (from dissertation_code.ipynb) is loaded using pickle.
o	The model is now ready to make predictions on new data (user inputs via the web interface).
3.	Input Fields for User Data:
o	Streamlit creates input fields for the user to enter the required features (e.g., transaction amount, V1, V2, ..., V28 features).
o	These input fields allow the user to simulate or provide real transaction data for fraud detection.
4.	Model Prediction:
o	When the user provides input and clicks a "Predict" button, the input data is passed to the Stacking Classifier.
o	The model makes a prediction: fraudulent (1) or non-fraudulent (0).
o	Based on the prediction, the web app displays either a success message (if the transaction is legitimate) or a warning (if fraud is detected).
5.	Web App Output:
o	The app shows whether the transaction is fraudulent or not.
o	It may also display some additional metrics, such as the probability of fraud, and provide information on how to interpret the prediction.
![image](https://github.com/user-attachments/assets/e74710d2-01df-4f5f-a44c-06c738bdc92b)
