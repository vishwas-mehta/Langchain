# Week 3 MLOps Assignment - Feast Feature Store Integration
---

## Overview
This assignment demonstrates the integration of Feast Feature Store into an Iris classification pipeline to ensure consistent feature usage across training and inference.

---

## Files Description

### `feature_store.ipynb`
The main notebook containing the complete pipeline implementation:
- Loads and prepares Iris dataset with timestamps and entity IDs
- Sets up GCP infrastructure (GCS, BigQuery, Firestore)
- Generates Feast configuration files
- Registers features with Feast
- Trains a DecisionTree model using Feast features
- Materializes features to online store for inference

### `iris_features.py`
Defines the feature definitions for Feast:
- Declares `iris_id` as the entity (unique flower identifier)
- Specifies BigQuery table as the data source
- Defines the 4 measurement features: `sep_len`, `sep_wid`, `pet_len`, `pet_wid`
- Sets feature TTL and schema

### `feature_store.yaml`
Feast configuration file that specifies:
- Project name and registry location
- GCP as the provider
- BigQuery as the offline store for historical features
- Datastore (Firestore) as the online store for real-time serving
- Entity serialization version

### `registry.db`
Feast's internal registry database that stores:
- Metadata about registered features
- Entity definitions
- Feature view configurations
- Data source information

### `iris_feast_ready.csv`
Processed Iris dataset prepared for Feast:
- Original 4 features (sepal/petal measurements)
- Species labels (`iris_type`)
- Temporal column (`timestamp`) for point-in-time lookups
- Entity identifier (`iris_id`) for each flower
- Created timestamp (`created_at`) for versioning

---

## How to Run
1. Open `feature_store.ipynb` in Vertex AI Workbench
2. Ensure GCP permissions are configured
3. Run all cells sequentially

---

## Results
- Model Accuracy: **93.33%**
- Features successfully registered and materialized
- Training-serving consistency achieved through Feast
