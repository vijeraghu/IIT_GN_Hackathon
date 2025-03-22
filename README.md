# IIT_GN_Hackathon
Hack The Future - 2025
The link of Github Repo is https://github.com/vijeraghu/IIT_GN_Hackathon 

Monthly Per Capita Expenditure Prediction Project: User Guide
This guide explains how to use our monthly per capita expenditure prediction project. It is divided into two sections: one for users interested in replicating the model and another for users who wish to obtain a prediction.

#**For Researchers and Developers**
1. Dataset Access
Action Required:
Download the datasets provided with the project.

**Instructions:**

**Step 1: Load the Saved Model**
import joblib
import pandas as pd
import numpy as np
import os

Load the saved model
loaded_model = joblib.load('models/sector_income_model.pkl')

Extract components from the loaded model
models = loaded_model['models']
feature_info = loaded_model['feature_info']

**Step 2: Load Your Test Data**

Path to your test data CSV file
test_data_path = 'path/to/your/test_data.csv'

 Load the test data
test_df = pd.read_csv(test_data_path)

**Step 3: Make Predictions**

from your_original_script import predict_for_new_data  # Import if in separate file

 Make predictions
Option 1: Using the path to the CSV file
result_df = predict_for_new_data(models, feature_info, test_data_path)

**Step 4: Save the Predictions**

Create a directory for results if it doesn't exist
if not os.path.exists('predictions'):
    os.makedirs('predictions')

 Save the predictions to a CSV file
result_df.to_csv('predictions/test_predictions.csv', index=False)

print("Predictions saved to 'predictions/test_predictions.csv'")

**Step 5: (Optional) Evaluate the Predictions if You Have Ground Truth**

If your test data contains the actual TotalExpense values
if 'TotalExpense' in test_df.columns:
    from sklearn.metrics import mean_squared_error, r2_score, mean_absolute_error
    
    # Calculate metrics
    mse = mean_squared_error(test_df['TotalExpense'], result_df['Predicted_TotalExpense'])
    rmse = np.sqrt(mse)
    mae = mean_absolute_error(test_df['TotalExpense'], result_df['Predicted_TotalExpense'])
    r2 = r2_score(test_df['TotalExpense'], result_df['Predicted_TotalExpense'])
    
    print(f"RMSE: {rmse:.2f}")
    print(f"MAE: {mae:.2f}")
    print(f"R²: {r2:.4f}")

#**For End Users**

**1. Visit the Website**
Action Required:
Click the provided link to access our website.
Instructions:
The website is designed to be user-friendly, allowing you to obtain your prediction without the need to install any software.

**2. Input Your Details**

Required Information:
Sector: The sector in which you live.
State: Your state of residence.
Religion: Your religious affiliation.
Social Group: Your social group classification.
Household Size: The number of individuals in your household.
Asset Ownership: Information about the assets you own.
Education Level: Your level of education.
Internet Usage: The proportion of household members who use the internet.
Online Purchases: The number of online purchases made in the last 365 days.
Instructions:
Fill in the required fields with the relevant information. This data is used to generate your monthly per capita expenditure prediction.

**3. Obtain Your Prediction**

Action Required:
Submit the information on the website.
Instructions:
After you provide your details, the system will process the data and display your monthly per capita expenditure prediction.
Conclusion
This project has been developed to be transparent and easy to use. Whether you are a researcher interested in the technical aspects of the model or an end user seeking a quick prediction, this guide provides clear instructions for each process. Please follow the steps carefully to achieve the desired outcomes.


**Contributions:**


3.1 Anirudh Chauhan

Name: Anirudh Chauhan
Email: anirudh.chauhan@plaksha.edu.in
Phone: 9548916156
Institution: Plaksha University
Major: Computer Science and Artificial Intelligence
Year: 2026
Contribution: Training and testing different ML models

3.2 Ayush Sharma

Name: Ayush Sharma
Email: ayush.sharma1@plaksha.edu.in
Phone: 8235853952
Institution: Plaksha University
Major: Computer Science and Artificial Intelligence
Year: 2026
Contribution: Preprocessing and Frontend

3.3 Japsahaj Kaur

Name: Japsahaj Kaur
Email: japsahaj.kaur@plaksha.edu.in
Phone: 9728000013
Institution: Plaksha University
Major: Computer Science and Artificial Intelligence
Year: 2026
Contribution: Worked on prediction of Individual Expenses

3.4 Rishav Kumar

Name: Rishav Kumar
Email: rishav.kumar@plaksha.edu.in
Phone: 8709490996
Institution: Plaksha University
Major: Computer Science and Artificial Intelligence
Year: 2026
Contribution: Training and testing on different models

3.5 Vijeta Raghuvanshi

Name: Vijeta Raghuvanshi
Email: vijeta.raghuvanshi@plaksha.edu.in
Phone: 8171227010
Institution: Plaksha University
Major: Computer Science and Artificial Intelligence
Year: 2026
Contribution: Dataset Preprocessing and Feature Engineering
