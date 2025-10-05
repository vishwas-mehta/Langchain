# IRIS Machine Learning Pipeline using Google Cloud Platform

This project demonstrates an end-to-end machine learning workflow implemented using the Iris dataset and integrated with Google Cloud Storage for data handling and artifact management. The workflow includes data retrieval, model training, artifact storage, and inference execution.

---

## Project Objectives

The primary objectives of this task were to:

1. Store the Iris training dataset in a Google Cloud Storage (GCS) bucket.  
2. Fetch the dataset from GCS and execute the Iris Machine Learning Training Pipeline.  
3. Store all output artifacts (models, logs, metrics, and predictions) in GCS, organized in folders named by their training execution timestamps.  
4. Develop a separate inference script to fetch trained models from the GCS output artifact directory and perform inference on an evaluation dataset.  
5. Execute the training and inference processes twice to demonstrate timestamp-based artifact organization.

---

## Files Included

- **train_pipeline.py** – Implements the complete training pipeline:
  - Fetches data from GCS.  
  - Preprocesses the dataset (splitting and scaling).  
  - Trains a Decision Tree Classifier.  
  - Evaluates the model and generates metrics.  
  - Saves and uploads artifacts to GCS under timestamped directories.

- **inference_pipeline.py** – Implements the inference pipeline:
  - Fetches the trained model and scaler from GCS.  
  - Prepares an evaluation dataset using the Iris data.  
  - Performs inference and computes accuracy.  
  - Saves and uploads inference results to GCS with proper timestamping.

- **reference_notebook.ipynb** – Contains a reference notebook illustrating the overall workflow.  
- **video_demo.mp4** – Demonstrates the execution of both training and inference pipelines.  
- **README.md** – Documentation file describing the project and implementation steps.

---

## Execution Summary

- The training and inference pipelines were executed twice.  
- Each execution generated a unique timestamped directory in the GCS bucket, verifying the automated versioning mechanism.  
- The video recording shows the complete execution process, including data retrieval, model training, artifact upload, and inference runs.

---

## Google Cloud Storage Structure

