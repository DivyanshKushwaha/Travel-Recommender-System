## AI-Powered Travel Recommendation System

The Smart Travel Recommendation System is an AI-powered feature designed to enhance the user experience by providing personalized travel destination recommendations based on user preferences, demographics, and past interactions.

**This system leverages machine learning algorithms such as:**

- Content-Based Filtering to suggest destinations similar to past preferences.
- Collaborative Filtering to recommend places based on similar user behaviors.
- Predictive Modeling to estimate how much a user might like a destination.
- A Flask-based web application has been developed to allow seamless user interaction with the AI model, enabling travelers to get customized travel suggestions based on their inputs.

### Objective of the Project
The goal of this project is to demonstrate AI capabilities beyond API-based solutions by developing a custom machine-learning pipeline that can:
- Analyze user preferences and past travel choices.
- Provide intelligent travel recommendations using ML models.
- Handle real-world data for effective personalization.
- Offer an interactive web-based experience via a Flask app.


### Project Structure
The project is structured as follows:

```bash
/AI-Travel-Recommendation-System
│── data/                  # Contains datasets (CSV files)
│── models/                # Trained machine learning models
│── app.py                 # Flask web application
│── demo.ipynb      # Jupyter Notebook (Model development)
│── final_df.csv           # Preprocessed and merged dataset
│── templates/             # HTML templates for Flask UI
│── README.md              # Project documentation

```


### Dataset and Preprocessing

We utilized four datasets to build a robust recommendation system downloaded from kaggle

- Dataset URL: 
```bash
https://www.kaggle.com/datasets/amanmehra23/travel-recommendation-dataset
```
- Dataset Description :
    - destinations.csv	Contains destination details (e.g., name, country, type, popularity).
    - reviews.csv	User reviews, ratings, and feedback on various destinations.
    - user_history.csv	Records past travel history, including visit dates and ratings.
    - users.csv	Demographic details of users (e.g., age, gender, preferences).
    - These datasets were merged and preprocessed to create a clean, structured dataset (final_df.csv) for model training.

## Data Cleaning Steps
- Handling missing values by imputing or dropping incomplete records.
- Removing duplicates to avoid biased recommendations.
- Feature engineering to extract relevant insights from raw data.
- One-hot encoding & label encoding for categorical variables.

## Model Development
This Recommendation system consists of three core techniques:

### 1. Content-Based Filtering

- Uses text similarity and metadata attributes to recommend destinations similar to past choices.
- Implementation:
    - TF-IDF Vectorization is applied to transform text-based metadata into numerical vectors.
    - Cosine Similarity measures how close two destinations are based on their attributes.
    - The system ranks and recommends top N similar destinations.

- Example Output:

    - If a user likes "Taj Mahal", the system suggests locations based on metadata similarities.

### 2. Collaborative Filtering

- Uses past user interactions and behavioral patterns to provide recommendations.
- Implementation:
    - Builds a User-Destination Interaction Matrix from user_history.csv.
    - Computes user similarity scores using Cosine Similarity.
    - Suggests destinations based on what similar users have enjoyed.

- Example Output:

    - If User A and User B have similar travel history, and User B loved "Kerala", the system recommends "Kerala" to User A.

### 3. Predictive Modeling for Personalized Suggestions

- Uses ML algorithms (RandomForestRegressor) to predict how much a user would enjoy a destination.
- Features: User demographics, travel history, ratings, and destination attributes.
- Training Process:

    - Splitting dataset into training & testing (80-20 ratio).
    - Hyperparameter tuning using GridSearchCV for optimal model performance.
    - Output: A predicted score (0-10) for each destination, tailored to the user.


### 4. Model Performance and Evaluation

- MSE (Mean Squared Error):	Measures prediction error for the ML model.
- R² Score:	Evaluates the predictive power of the model.

## Results
- Content-Based Filtering provides highly relevant recommendations.
- Collaborative Filtering adapts well to different user preferences.
- Predictive Model achieves:

    - MSE: Low (indicating accurate predictions)
    - R² Score: High (suggesting strong correlation between features and ratings)


## Flask Web Application
- User-friendly interface for inputting travel preferences.
- Real-time recommendations based on user input.
- Backend powered by Flask, serving ML model predictions via API endpoints.

### How It Works
- User enters travel preferences (location, age, past destinations).
- Flask processes input and queries the ML model.
- Personalized recommendations are displayed.

## Scalability and Future Enhancements
- Optimized ML models for handling large-scale data.
- Parallel computations for faster response times.
- Cloud-based deployment (AWS/GCP) for real-world use.

## Future Enhancements
- Real-time Weather Integration for better recommendations.
- Deep Learning-based Recommender Systems (Neural Networks).
- Mobile App Version for a seamless user experience.

## Conclusion
This AI-powered travel recommendation system enhances user experience through intelligent, data-driven recommendations. Using a combination of content-based, collaborative filtering, and predictive modeling, the system provides personalized suggestions that can scale to real-world applications.