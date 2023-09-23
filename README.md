# Cardio Care Predictor API

![Python](https://badgen.net/badge/Python/3.7/orange)
![License](https://badgen.net/badge/license/MIT/blue)

- Flask REST API which predicts the probability of Coronary Heart Disease in a patient taking 9 different parameters based on the patient's history as input.
- The API uses a Logistic Regression Model from sci-kit-learn trained on the [Framingham Heart Study Dataset](https://www.kaggle.com/amanajmera1/framingham-heart-study-dataset) from Kaggle.
- The model achieved a test accuracy of around 88%.

## Useful Links

- Deployed on OnRender: [Onrender Link](https://cardio-care-predictor-api.onrender.com/)
- View the Jupyter Notebook: [Jupyter Notebook](https://github.com/amansrv/Cardio-Care-Predictor-API/blob/main/model/HeartDisease.ipynb)
- Flask REST API: [API](https://github.com/amansrv/Cardio-Care-Predictor-API/blob/main/app.py)

## Predict Endpoint

- Takes 9 parameters as input
- Returns a binary prediction (0 or 1) and probability as well.

	### Sample query
    	https://cardio-care-predictor-api.onrender.com/predict?age=31&sex=1&cigs=5&chol=230&sBP=280&dia=0&dBP=90&gluc=87&hRate=84

	### Sample output

      {
         "data":{
            "age": "31",
            "cigsPerDay": "5",
            "diaBP": "90",
            "diabetes": "0",
            "glucose": "87",
            "heartRate": "84",
            "sex": "1",
            "sysBP": "280",
            "totChol": "230"
         },
         "prediction":[
            1
         ],
         "probability":[
            [
               0.4587093009776524,
               0.5412906990223476
            ]
         ]
      }


## Model Endpoint
- Returns the model details such as intercept and coefficients.

		https://cardio-care-predictor-api.onrender.com/model

## Running locally

1. Clone the repository

   ```bash
      git clone https://github.com/amansrv/Cardio-Care-Predictor-API.git
	
      cd Cardio-Care-Predictor-API
   ```
2. Install dependencies
   ```bash
	   pip install requirements.txt
   ```
	
3. Start the Flask server
   ```bash
	   python3 app.py
   ```
