# 🧠 Multiple Disease Prediction System using Machine Learning via Streamlit

> Predict Parkinson’s, Heart Disease, and Breast Cancer from medical inputs using trained ML models.

This project uses three different machine learning models trained on respective biomedical datasets to predict the likelihood of three diseases:
- Parkinson’s Disease
- Heart Disease
- Breast Cancer (Malignant or Benign)

Each model takes a specific set of clinical features and outputs whether the disease is likely to be present.

Here is a snapshot of the working Streamlit site:

![image](https://github.com/user-attachments/assets/9d29f52e-3917-4dcc-bf12-18745586a408)

---

## Datasets Used

### Parkinson’s Disease Dataset
- **Source**: UCI Machine Learning Repository
- **Samples**: 195 voice recordings from 31 individuals
- **Features**: 22 voice-measurement features
- **Target**: 0 = Healthy, 1 = Parkinson’s

### Heart Disease Dataset
- **Source**: UCI Cleveland Heart Disease Dataset
- **Samples**: 303 patient records
- **Features**: 13 numerical/categorical health indicators
- **Target**: 0 = No Heart Disease, 1 = Heart Disease Present

### Breast Cancer Dataset
- **Source**: sklearn.datasets.load_breast_cancer()
- **Samples**: 569 cases
- **Features**: 30 tumor-related metrics
- **Target**: 0 = Malignant, 1 = Benign

---

## Technologies Used

- `numpy` – Numerical operations  
- `pandas` – Data manipulation  
- `scikit-learn` – Model training & evaluation  
- `pickle` – Model serialization  
- `matplotlib` (optional) – Visualization

---

## Workflow

### 1. Model Training (Done Separately)
Each model was trained independently on its dataset. Preprocessing steps included:
- Handling missing values
- Encoding categorical variables (if needed)
- Feature scaling
- Model selection via cross-validation

Trained models were saved as `.sav` files using `pickle`.

### 2. Prediction Script
The final script:
- Loads each `.sav` file using `pickle`
- Accepts user input for relevant features
- Converts input into correct format
- Makes prediction via the loaded model

Each disease has its own input format and prediction logic.

---

## Example Prediction (Parkinson’s)

```python
input_data = [119.992, 157.302, 74.997, 0.00784, 0.00007, 0.00370, 0.00554,
              0.00921, 0.04374, 0.426, 0.0204, 0.0095, 0.0135, 0.0179, 0.0037,
              21.033, 0.414783, 0.815285, -4.813031, 0.266482, 2.301442, 0.284654]

model = pickle.load(open('parkinsons_model.sav', 'rb'))
prediction = model.predict([input_data])
```

**output**
```bash
[1] → The person has Parkinson's Disease
```

## How to Run the Streamlit App

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)

---

### Step-by-Step Installation

#### 1. Clone the repository
```bash
git clone https://github.com/your-username/parkinsons-disease-prediction.git
cd parkinsons-disease-prediction
```
#### 2. Create and activate a virtual environment
```bash
python -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate
```
#### 3. Install dependencies
```bash
pip install -r requirements.txt
```
#### 4. Save the script in your machine 
download the multiple-disease-pred.py file in your folder from the repo.
#### 5. Run the script using commands.txt
```bash
streamlit run \your\saved\py\script\path
```

