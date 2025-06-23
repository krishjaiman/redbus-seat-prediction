# redbus-seat-prediction
Redbus Seat Count Prediction (15 Days Prior)
This project was developed as part of the Redbus Data Decode Hackathon. The objective was to predict the total number of seats that would be booked on a bus journey 15 days before the journey date, using historical transaction and route data.

📌 Problem Statement
The task was to build a predictive model that estimates the final seat count for a journey 15 days in advance, leveraging booking trends, search data, and route-specific characteristics.

🔍 Dataset
The following datasets were provided:

transactions.csv: Contains cumulative seat and search counts along with booking details per journey.

train.csv: Contains final seat counts (target variable) for journeys from March 2023 to December 2024.

test.csv: Contains journey details where seat counts need to be predicted.

sample_submission.csv: Format for the final submission.

⚠️ Note: The datasets were provided exclusively for hackathon participants and cannot be shared publicly. Please contact the organizers for dataset access.

🛠️ Solution Overview
Data Preparation: Merged transactional features for each journey 15 days before departure.

Feature Engineering:

Cumulative seat and search counts.

Day of the week.

City-level regions and tiers.

Residual Modeling: Predicted the difference between route-wise mean seat counts and actual bookings.

Log Transformation: Applied to stabilize variance and handle large booking scales.

Weighted Loss: Used sample weights to reduce bias towards small seat counts.

Modeling: Trained a LightGBM regressor with hyperparameter tuning using Optuna.

Robust Test Pipeline: Included handling of unseen categorical labels and feature alignment.

🚀 Achievements
Reduced RMSE from ~600 to 307 using weighted residual modeling and log transformation.

Successfully captured seasonality and route-specific trends.

Developed a fully reproducible, submission-ready pipeline.

Key libraries:

pandas

numpy

lightgbm

optuna

scikit-learn

seaborn

matplotlib

📂 Usage
You can run the notebook seat_count_prediction.ipynb step-by-step:

Load the datasets.

Prepare features and weights.

Train the LightGBM model.

Predict on test data.

Generate the final submission file.

📢 Notes
The actual datasets cannot be shared due to hackathon data restrictions.

The pipeline includes handling of unseen labels and missing features in the test set.

✨ Acknowledgements
Thanks to Redbus and the Data Decode Hackathon team for organizing this competition and providing a valuable learning experience in predictive modeling and real-world data challenges.

