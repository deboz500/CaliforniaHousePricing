# California House Pricing Prediction

A Flask web app that predicts house prices in California based on block group-level features using a saved regression model.

## Project Overview

This application allows users to submit the following features through a web form and receive a predicted house price:

- `MedInc`: median income in block group
- `HouseAge`: median house age in block group
- `AveRooms`: average number of rooms per household
- `AveBedrms`: average number of bedrooms per household
- `Population`: block group population
- `AveOccup`: average number of household members
- `Latitude`: block group latitude
- `Longitude`: block group longitude

The app uses a pre-trained regression model (`regmodel.pkl`) and a scaler (`scaling.pkl`) to process input and return predictions.

## Requirements

- Python 3.7 or later
- Flask
- pandas
- scikit-learn
- numpy
- matplotlib
- seaborn

## Installation

1. Clone the repository:

```bash
git clone https://github.com/deboz500/CaliforniaHousePricing.git
cd CaliforniaHousePricing
```

2. Create and activate a virtual environment:

For Anaconda users:

```bash
conda create -p venv python==3.7 -y
conda activate ./venv
```

For other users:

```bash
py -3 -m venv venv
.\venv\Scripts\activate.bat
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

## Usage

1. Start the Flask application:

```bash
python app.py
```

2. Open a browser and go to:

```text
http://127.0.0.1:5000/
```

3. Fill in the form fields and click the **Predict** button.

## Web Form

The home page form is built in `templates/home.html` and includes Bootstrap styling.
Each input field is required and uses its variable name as the placeholder.

## API Endpoints

- `GET /`: renders the home page with the prediction form.
- `POST /predict`: accepts form data and returns a rendered page with the prediction.
- `POST /predict_api`: accepts JSON data in the format:

```json
{
  "data": {
    "MedInc": 8.3252,
    "HouseAge": 41.0,
    "AveRooms": 6.9841,
    "AveBedrms": 1.0238,
    "Population": 322.0,
    "AveOccup": 2.5556,
    "Latitude": 37.88,
    "Longitude": -122.23
  }
}
```

and returns the prediction as JSON.

## Notes

- Ensure `regmodel.pkl` and `scaling.pkl` are present in the project root.
- The app runs in debug mode by default in `app.py`.

## Git Configuration (Optional)

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## Deployment

You can deploy this app to Heroku or any Python-compatible hosting service by ensuring the required files are available and setting the correct `FLASK_APP=app.py` environment variable.



