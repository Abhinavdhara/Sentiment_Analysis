# Sentiment_Analysis
# Sentiment Analysis Web Application

This project is a Flask-based web application that provides sentiment analysis on input text. It uses a pre-trained machine learning model to classify text into sentiment categories.

Features
- User-Friendly API: Input text via a simple POST request and receive sentiment predictions.
- **Machine Learning Model**: A pre-trained sentiment analysis model loaded using `joblib`.
- **Deployable**: Ready for deployment on Heroku or similar platforms.

## Requirements
- Python 3.8+
- Flask
- Gunicorn
- Joblib

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-repo/sentiment-analysis-app.git
   cd sentiment-analysis-app
   ```

2. Create a virtual environment and activate it:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Ensure the pre-trained model `sentiment_model.pkl` is in the root directory.

## Usage

### Run Locally
1. Start the Flask development server:
   ```bash
   python app.py
   ```

2. Open the application:
   - By default, the app will run on `http://127.0.0.1:5000`.

3. Make a prediction:
   - Use a tool like Postman or `curl` to send a POST request:
     ```bash
     curl -X POST -H "Content-Type: application/json" -d '{"text": "Your input text here"}' http://127.0.0.1:5000/predict
     ```

4. You will receive a response like:
   ```json
   {"prediction": 4}
   ```

### Deployment on Heroku
1. Install the Heroku CLI and log in:
   ```bash
   heroku login
   ```

2. Create a new Heroku application:
   ```bash
   heroku create
   ```

3. Push the application to Heroku:
   ```bash
   git push heroku master
   ```

4. Open the deployed application:
   ```bash
   heroku open
   ```

## Project Structure
```
.
├── app.py               # Main application file
├── sentiment_model.pkl  # Pre-trained ML model
├── requirements.txt     # Python dependencies
├── Procfile             # For Heroku deployment
├── runtime.txt          # (Optional) Python version for Heroku
└── README.md            # Project documentation
```

## Model Details
The model used in this project is pre-trained and stored as `sentiment_model.pkl`. It was trained on a dataset of labeled text data to predict sentiment. The categories are:
- 0: Negative
- 4: Positive

## Future Improvements
- Add a frontend for user interaction.
- Improve model accuracy by fine-tuning.
- Expand to support additional sentiment categories.

## Contributing
Feel free to fork this repository, make enhancements, and submit a pull request. Contributions are always welcome!

## Acknowledgments
- [Flask Documentation](https://flask.palletsprojects.com/)
- [Heroku Deployment Guide](https://devcenter.heroku.com/articles/getting-started-with-python)
- [Joblib Documentation](https://joblib.readthedocs.io/)

