Insurance Premium Prediction API


A machine learning API built with FastAPI for predicting insurance premiums based on patient data. The system includes a trained ML model, Docker support for easy deployment, and a RESTful interface for predictions.

✨ Features
FastAPI Backend: High-performance, modern Python web framework

Machine Learning Model: Trained model for insurance premium prediction

Docker Support: Containerized deployment with Dockerfile

Data Validation: Pydantic schemas for request/response validation

Example Data: Includes sample datasets (insurance.csv, patients.json)

Jupyter Notebook: Interactive model training and exploration

Local Installation
Clone the repository:

bash
git clone https://github.com/yaniv-11/Insurance-Premium-Prediction.git
cd Insurance-Premium-Prediction
Install dependencies:

bash
pip install -r requirements.txt
Run the application:

bash
uvicorn app:app --reload

🚀 Usage
Once the server is running (default: http://localhost:8000), you can:

Access the interactive API documentation:

Swagger UI: http://localhost:8000/docs

ReDoc: http://localhost:8000/redoc

Test the API using the sample data in patients.json

Make predictions via HTTP requests to the /predict endpoint

🔌 API Endpoints
POST /predict
Predict insurance premium based on patient data.

Request Body:

json
{
  "age": 45,
  "sex": "male",
  "bmi": 25.5,
  "children": 2,
  "smoker": "no",
  "region": "southeast"
}
Response:

json
{
  "predicted_premium": 8500.75,
  "status": "success"
}
GET /health
Check API health status.

Response:

json
{
  "status": "healthy",
  "timestamp": "2025-12-25T10:30:00Z"
}
🤖 Model Training
The machine learning model was developed in the fastapi_ml_model.ipynb Jupyter notebook, which includes:

Data exploration and preprocessing

Feature engineering

Model training and evaluation

Hyperparameter tuning

Model serialization for API use

Key steps in the notebook:

Loading and exploring insurance.csv

Handling categorical variables (sex, smoker, region)

Splitting data into training/testing sets

Training regression models

Model evaluation and selection

🐳 Docker Deployment
The project includes a Dockerfile for containerized deployment:

Build the Docker image:
bash
docker build -t insurance-prediction-api .
Run the container:
bash
docker run -p 8000:8000 insurance-prediction-api

📊 Dataset
The model is trained on the insurance.csv dataset containing:

age: Age of primary beneficiary

sex: Gender (male/female)

bmi: Body mass index

children: Number of dependents

smoker: Smoking status (yes/no)

region: Residential area (northeast, northwest, southeast, southwest)

charges: Individual medical costs (target variable)
