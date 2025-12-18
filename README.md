💊 Disease Prediction using Symptoms
This project is a machine learning–based disease prediction system that takes common symptoms as input and predicts a probable disease (prognosis). It is built in Python using pandas, scikit‑learn, and Gradio for an interactive web interface.​

📌 Project Overview
Uses a medical symptom dataset where each row represents a patient and each column is a binary symptom (0 or 1).​

The target column prognosis contains the disease label (e.g., Allergy, GERD, Fungal infection, Drug Reaction, Chronic cholestasis).​

A supervised classification model is trained to map symptom vectors to disease labels.​

🧠 Model and Approach
Data is loaded and explored using pandas (df.head(), df.info(), df.isnull().sum()).​

The dataset has 133 columns in total: 132 integer symptom features and 1 object column for prognosis, with no missing values across all columns.​

Features (X) and labels (y) are created by dropping the prognosis column from the dataframe and using it as the target.​

A machine learning pipeline is then applied:

Train–test split is used to evaluate the model on unseen data.​

Features are scaled with a scaler object and the trained model is saved as model.pkl, along with scaler.pkl and X_train_columns.pkl for later inference.​

A prediction function predict_disease(...) takes key symptoms (itching, skin_rash, nodal_skin_eruptions, continuous_sneezing, shivering, chills, joint_pain, stomach_pain, acidity, ulcers_on_tongue, muscle_wasting, vomiting, burning_micturition, spotting_urination, fatigue, weight_gain, anxiety, cold_hands_and_feets, mood_swings, weight_loss), builds a pandas DataFrame, applies preprocessing, and returns the predicted disease as text.​

🌐 Gradio Web App
To make the model interactive, a Gradio interface is created:​

The app exposes 20 numeric input fields (0/1 or severity value) corresponding to the main symptoms.​

The backend calls predict_disease and displays the output disease name as text.

🛠️ Tech Stack
Python 3​

pandas for data handling​

scikit‑learn for preprocessing and modeling (scaler, classifier, train–test split)​

pickle for model persistence (model.pkl, scaler.pkl, X_train_columns.pkl)​

Gradio for building the web interface​

🚀 How to Run Locally
Clone this repository and navigate into it.

Install dependencies (example):

*bash
pip install -r requirements.txt*

Make sure the dataset CSV (e.g., Testing.csv) is available in the expected path used in the notebook/code.​

Run the notebook/script to train and save the model, or keep the provided model.pkl, scaler.pkl, and X_train_columns.pkl.​

Start the Gradio app (e.g., by running the corresponding .py script or notebook cell with interface.launch()).​

Open the provided local or public URL to use the Disease Predictor UI.​

⚠️ Disclaimer
This project is for educational and experimental purposes only and is not a substitute for professional medical advice, diagnosis, or treatment. 
Always consult a qualified healthcare provider for medical decisions
