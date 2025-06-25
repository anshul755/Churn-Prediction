__Churn Prediction Web App__  
A Streamlit-based application for predicting customer churn and salary estimation using regression and classification models trained on the Churn Modelling dataset.  

**🌐 Live Demos**  
- [Regression App](https://annchurnregression.streamlit.app/)  
- [Classification App](https://annchurnpredictorclassifier.streamlit.app/)  

## Table of Contents  
- [Project Overview](#project-overview)  
- [Features](#features)  
- [Getting Started](#getting-started)  
  - [Prerequisites](#prerequisites)  
  - [Installation](#installation)  
- [Usage](#usage)  
  - [Running the App](#running-the-app)  
  - [Streamlit Interface](#streamlit-interface)  
- [Model Artifacts](#model-artifacts)  
- [TensorBoard](#tensorboard)  
- [Dependencies](#dependencies)  

---  

## Project Overview  
This repository contains two customer churn prediction pipelines built on the Churn Modelling dataset:  
1. **Regression model** to estimate customer’s estimated salary (regression task).  
2. **Classification model** to predict whether a customer will churn (binary classification task).  

Both pipelines include data preprocessing, model training using `tensorflow.keras`, and a Streamlit UI for interactive input and real-time predictions.  

## Features  
- **Interactive UI**: Select input features and get live predictions in Streamlit.  
- **Dual Pipelines**: Separate workflows for regression and classification.  
- **Preprocessing**: Label encoding, one-hot encoding, and feature scaling included via `pickle` artifacts.  
- **TensorBoard Integration**: Monitor training metrics and loss curves.  

## Getting Started

### Installation  
1. Clone the repository:  
   ```bash
   git clone https://github.com/anshul755/Churn-Prediction.git
   cd Churn-Prediction
   ```  
2. Create and activate a virtual environment (optional but recommended):  
   ```bash
   python3.10 -m venv tf310
   source tf310/bin/activate      # Linux/macOS
   tf310\Scripts\activate         # Windows
   ```  
3. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```  

## Usage  
### Running the App  
- **Regression App**:  
  ```bash
  streamlit run app_regression.py
  ```  
- **Classification App**:  
  ```bash
  streamlit run app_classification.py
  ```  

### Streamlit Interface  
1. **Geography**: Select customer’s country.  
2. **Gender**: Choose customer’s gender.  
3. **Age**, **Balance**, **Credit Score**: Input numeric features via sliders or input fields.  
4. **Other Features**: Tenure, number of products, active member flag, etc.  
5. **Predict** button: View the model’s output (estimated salary or churn probability/label).  

## Model Artifacts  
Trained models and preprocessing objects are stored in the `models/` directory:  
- `.h5` files: Keras model weights for regression and classification.  
- `.pkl` files: `LabelEncoder`, `OneHotEncoder`, and `StandardScaler` instances used at inference time.  

## TensorBoard  
To visualize training logs:  
```bash
tensorboard --logdir logs/fit  # Regression logs
tensorboard --logdir regression/fit  # Classification logs
```  
Open `http://localhost:6006` in your browser.  

## Dependencies  
- `pandas`  
- `numpy`  
- `scikit-learn`  
- `tensorflow`
- `pickle`  
- `streamlit`  

Refer to `requirements.txt` for exact versions.
