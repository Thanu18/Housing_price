### Housing_price

### Software and Tools Requirements

1. [Github Account](https://github.com)
2. [HerokuAccount] (https://heroku.com)
3. [VSCodeIDE] (https://code.visualstudio.com/)
4. [GitCLI] (https://www.git-scm.com/downloads)

### Prerequesties

-- Python 3.7+
-- Pip(Python package Installer)
-- Docker
-- Heroku CLI

### Clone the Repository

'''bash
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name

### Set Up the Python Environment

1. Create a virtual environment
'''
conda create -p myenv python=3.7 -y
'''

2. Activate the virtual environment
'''
conda activate myenv /.
'''

3. Install the dependencies
'''
pip install -r requirements.txt
'''

## Usage
1. Ensure the Databse available
2. Run the script to train the linear regrssion model
'''
python Linear_Regression_ML_Implemantation.py
'''
3. The trained model will be saved as regmodel.pkl and the scaling parametes will be saved as scaling.pkl

### Run the Flask Application

1. Start the Flask app:
'''
python app.py
'''

2. The app will be running at 'http://127.0.0.1:5000/' with the home.html template 

### Endpoints

- Home: GET /
    - Returns a welcome message.
- Predict: POST /predict
    - Accepts a JSON payload with features and returns the prediction.

### Testing

1. Open Postman
2. Create new POST request to 'http://127.0.0.1:5000/predict'
3. In the body, use raw JSON and provide necessay features
    '''
    {"data":{
    "MedInc":8.9252,
    "HouseAge":41.0,
    "AveRooms":6.984127,
    "AveBedrms":1.023810, 
    "Population":322.0,
    "AveOccup":2.555556, 
    "Latitude":37.88,
    "Longitude":-122.23
    }
    }
'''
4. Send the request and check the responses

### Docker
Build the Docker image with the following in the Dockerfile
'''
    FROM python:3.7
    COPY . /app
    WORKDIR /app
    RUN pip install -r requirements.txt
    EXPOSE $PORT
    CMD gunicorn --workers=4 --bind 0.0.0.0:$PORT app:app
'''

### Deployment with GitHub Actions
1. Log in to Heroku
2. Create a new Heroku app
3. Create a '.github/workflows' directory in your project root.
4. Create a workflow file named 'main.yaml' inside the '.github/workflows'  directory
5. Commit the changes to GitHub
6. In your repository, In your GitHub repository, go to Settings > Secrets and add the following secret:
    - HEROKU_API_KEY: Your Heroku API key. You can find it in your Heroku account settings.
    - HEROKU_APP_NAME: The name of the APP
    - HEROKU_EMAIL: Your Email address
7. Push the changes to the main branch
'''
    git add .
    git commit -m "Add GitHub Actions workflow for Heroku deployment"
    git push origin main
'''


