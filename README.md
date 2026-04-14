# Student Graduation Prediction System

## Overview

This project is a machine learning–based web application designed to predict whether a student will pass or not based on academic performance and related factors. The system uses a trained classification model and provides an interactive interface for uploading student data and generating predictions.

The application is built using Python and Streamlit, allowing users to easily upload CSV data, process it, and download prediction results.

## Features

Machine Learning Prediction

* Predict student graduation outcome (Lulus / Tidak Lulus)
* Uses Random Forest Classifier
* Supports batch prediction using CSV input

Feature Engineering

* Automatically generates additional features:

  * Average score (RataRata)
  * Total score (TotalNilai)
  * Score category (NilaiKategori)

Model Training

* Hyperparameter tuning using GridSearchCV
* Cross-validation for model evaluation
* Balanced class handling

Interactive Web Interface

* Upload CSV file for prediction
* Display input data and prediction results
* Download prediction results as CSV

Output Generation

* Adds prediction results to dataset
* Saves output as hasil_prediksi.csv

## Tech Stack

Programming Language: Python
Framework: Streamlit
Machine Learning: scikit-learn (Random Forest)
Data Processing: pandas, numpy
Model Persistence: joblib

## Project Structure

* app.py → Streamlit application for prediction
* train_model.py → script for training the model
* model_prediksi.pkl → saved trained model
* data_latih_dummy.csv → training dataset
* data_uji.csv → sample test dataset
* hasil_prediksi.csv → output prediction file
* requirements.txt → project dependencies

## Input Data Format

The input CSV must contain the following columns:

* Siswa
* Matematika
* Bahasa
* IPA
* Kehadiran
* Tugas

Example:

Siswa,Matematika,Bahasa,IPA,Kehadiran,Tugas

The system will automatically generate additional features during processing.

## How to Run

1. Install dependencies:

```bash
pip install -r requirements.txt
```

2. Run the Streamlit app:

```bash
streamlit run app.py
```

3. Open the browser link provided by Streamlit

4. Upload a CSV file with the required format

5. View prediction results and download the output file

## Model Training

To retrain the model:

```bash
python train_model.py
```

This will:

* process training data
* train the model using Random Forest
* perform hyperparameter tuning
* evaluate model performance
* save the model as model_prediksi.pkl

## How to Run (Web Version)

You can also use the application directly without installing anything via Streamlit Cloud:

Open the app in your browser:

```bash
https://prediksi-siswa.streamlit.app/
```

Steps:

1. Open the link above
2. Upload a CSV file with the required format
3. View prediction results
4. Download the generated output file

## System Workflow

1. Prepare training dataset
2. Run training script to generate model
3. Launch Streamlit application
4. Upload test dataset (CSV)
5. System processes input and generates features
6. Model predicts graduation outcome
7. Results are displayed and saved
8. User downloads prediction file

## Notes

* The model expects all required columns in the input file
* The system does not handle missing values automatically
* The preprocessing step is performed separately in both training and prediction
* The output file will be overwritten each time the system runs
* Ensure the trained model file (model_prediksi.pkl) is available before running the app

## Author

Abdan Nawwaf El Hibban, M. Hisyam Al Firdaus