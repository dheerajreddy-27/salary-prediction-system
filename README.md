# Workforce Salary Prediction System

This is a complete end-to-end Machine Learning project that predicts an employee's expected salary based on their workforce data, constructed with a Python FastAPI backend and a React (Vite) frontend.

## Features
- **Data Preprocessing**: Handles missing values, performs one-hot encoding on categorical data, and scales numerical values.
- **Machine Learning**: Evaluates multiple models (Linear Regression, Random Forest, Decision Tree, Gradient Boosting) and selects the one with the highest R² score (currently Gradient Boosting).
- **API Backend**: FastAPI endpoints for predictions (single, batch, and resume parsing).
- **Web UI & Visualization**: Interactive user interface via React. Provides intuitive forms, bulk processing CSV uploads, and resume analysis directly on the browser.

## Project Structure
- `backend/`: FastAPI application code.
  - `generate_data.py`: A utility script to generate `dataset.csv` with synthetic workforce data.
  - `dataset.csv`: Example dataset with columns such as Age, Job Role, Experience, Location, and Salary.
  - `data_preprocessing.py`: Contains the `scikit-learn` ColumnTransformer and Pipeline objects handling encoding, imputation, and feature scaling.
  - `model_training.py`: Model loader which fits regressors using preprocessed data, evaluates them, and saves the best model as `model.joblib`.
  - `salary_prediction.py`: Loads the model and wraps it into a Python backend API logic for usage.
  - `app.py`: FastAPI server allowing predictions, batch processing, and resume extraction.
- `frontend/`: React + Vite frontend application.
  - `src/App.jsx`: Main React application containing UI tabs for Single Prediction, Bulk Assessment, and AI Resume Analysis.

## Step-by-Step Instructions to Run the Project

### 1. Run the Backend (FastAPI)
1. **Navigate to the backend directory and set up a virtual environment**:
   ```bash
   cd backend
   python3 -m venv .venv
   source .venv/bin/activate
   ```
2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
3. **Generate Dataset & Train the ML Model** (if not already trained):
   ```bash
   python generate_data.py
   python model_training.py
   ```
4. **Start the API Server**:
   ```bash
   python app.py
   ```
   The backend will be running at `http://localhost:8000`.

### 2. Run the Frontend (React / Vite)
1. **Navigate to the frontend directory**:
   ```bash
   cd frontend
   ```
2. **Install packages & run the development server**:
   ```bash
   npm install
   npm run dev
   ```
   The frontend will be running at `http://localhost:5173`.

