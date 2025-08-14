# Diabetes Prediction App
This is a web application built with Streamlit that predicts the likelihood of a patient having diabetes based on various health parameters.  
The app uses a machine learning model trained with PyCaret to classify the result into **Positive Diabetes** or **Negative Diabetes**.

## Features
- Interactive web interface for input parameters  
- Real-time prediction  
- Support for 7 input parameters:
  - Pregnancies
  - Glucose
  - Blood Pressure
  - Skin Thickness
  - BMI (Body Mass Index)
  - Diabetes Pedigree Function
  - Age  
- Automatic creation of an additional feature `BMI_Age_Interaction` for better prediction accuracy

## Installation
1. Clone this repository or download the project folder.
2. Create a virtual environment:
```bash
python -m venv venv
```
3. Activate the virtual environment:
```bash
# Windows
venv\Scripts\activate
# Mac/Linux
source venv/bin/activate
```
4. Install required packages:
```bash
pip install streamlit pandas pycaret imbalanced-learn
```
(Optional) Install **cuml** for GPU acceleration:
```bash
pip install cuml
```

## Usage
1. Make sure `app.py` and the trained model file `model.pkl` are in the same folder.
2. Run the Streamlit app:
```bash
streamlit run app.py
```
3. Enter the patient parameters in the input fields.
4. Click **"Prediksi"** to see the result.

## Required Parameters
| Parameter                   | Range/Values     | Description |
|-----------------------------|------------------|-------------|
| Pregnancies                 | 0–20             | Number of pregnancies |
| Glucose                     | 0–300            | Plasma glucose concentration |
| Blood Pressure              | 0–200            | Blood pressure level (mm Hg) |
| Skin Thickness              | 0–100            | Skin fold thickness (mm) |
| BMI                         | 0.0–70.0         | Body Mass Index |
| Diabetes Pedigree Function  | 0.0–3.0          | Function score indicating family history |
| Age                         | 0–120            | Age in years |

**Note:** The app automatically calculates `BMI_Age_Interaction` by multiplying BMI and Age.

## Dependencies
- Python 3.11+
- streamlit
- pandas
- pycaret
- imbalanced-learn (for model training using SMOTE)

## Model
The application uses a pre-trained PyCaret classification model (`model.pkl`) trained on the Pima Indians Diabetes Dataset with additional preprocessing, feature engineering, and SMOTE balancing.

## License
This project is licensed under the MIT License - see the LICENSE file for details.
