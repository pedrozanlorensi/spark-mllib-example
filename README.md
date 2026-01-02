# Linear Regression Inference with MLflow on Databricks

## Overview
This notebook demonstrates two approaches for running distributed inferences using a registered Spark MLlib model with MLflow on Databricks (AWS, Spark 15.4.x-scala2.12):

1. **Approach 1:** Load the model with `mlflow.spark.load_model` and use `.transform()` for predictions.
2. **Approach 2:** Use `mlflow.pyfunc.spark_udf` to create a UDF for distributed predictions.

## Workflow Steps
- Create sample data.
- Train and log sample model.
- Load a registered MLflow model from Unity Catalog.
- Run predictions on input features using both approaches.
- Save prediction results to Unity Catalog tables.
- Measure and compare inference times.

## Key Paths and Tables
- Note that these tables/directory/model can be changed using the variables defined in code. 
- **Model URI:** `model_uri` (update as needed)
- **Temporary Directory:** `/Volumes/pedroz_catalog/mlops_schema/temp_dir`
- **Prediction Tables:**
  - `pedroz_catalog.mlops_schema.linear_regression_predictions_load_transform`
  - `pedroz_catalog.mlops_schema.linear_regression_predictions_udf`

## Requirements
- Databricks cluster (AWS, Spark 15.4.x-scala2.12)
- MLflow and PySpark libraries
- Unity Catalog enabled

## Usage
1. Update the input variables as needed.
2. Run all cells sequentially.
3. Compare inference times for both approaches.

## Notes
- Temporary resources are stored in `/Volumes/pedroz_catalog/mlops_schema/temp_dir` and will be cleaned up after usage.
- All outputs are saved to Unity Catalog tables for easy access and sharing.