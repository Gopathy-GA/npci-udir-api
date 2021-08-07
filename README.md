# npci-udir-api
Source code of API for NPCI
version: 0.2

Pre-requisites

Steps for local environment setup & execution:
==============================================
1.) Python 3.6 or higher version is a must
2.) Install Git Bash (for Windows if not already installed)
3.) Install "tox" virtual environment using the command: pip install tox
4.) Run the terminal or Git Bash (run as admin)
5.) Navigate to your working folder or directory
6.) Clone the repo using the command: git clone <the repository url>
7.) Open editor of your choice and load the cloned git folder into the editor
8.) To start the API server, use the command: tox -e run
9.) Go to browser to test the API using: localhost:8001
10.) To execute automated unit test scripts, run the command: tox -e test_app

Deploy to Cloud environment (Heroku):
====================================
1.) To the deploy the API into Heroku cloud environment,
    a.) Go to www.heroku.com and
    b.) Create an account
2.) Download the Heroku Command Line Interface(CLI) from the url: https://devcenter.heroku.com and install it in your local machine
3.) Test the Heroku CLI with the command: heroku --version
4.) Create an app using Heroku CLI with the command: heroku create
15.) Provide Heroku credentials when prompted
6.) Ensure that you are in your cloned git repository
7.) Push the git folder to Heroku using the command: git push heroku master
8.) Observe the progress prompts and look out for errors, if any
9.) If no errors, you should get the following info:
        "Verifying deploy... done."
        "To https://git.heroku.com/<your heroku app name>.git"
10.) Go to the Heroku site and click on your app to view the details
11.) Click on the "Open App" button to view and test the deployed API on the browser
12.) To verify the deployed API from the terminal or Git Bash, copy the "curl" content form the browser
and paste & execute it in the terminal or Git Bash. Verify the output
13.) Verify Heroku logs using the command: heroku logs --tail

Enable CI/CD with circleci:
==========================
1.) Visit: https://circleci.com  
2.) Ensure that :.circleci/config.yml" is present under npci-udir-api folder and is present in the GitHub repository
3.) Sign up using your GitHub credentials
4.) Create the environment variables named HEROKU_API_KEY and HEROKU_APP_NAME in the "Project Settings" tab
5.) Copy the API key from the "Account Settings" on HEROKU and paste in the "value" text box of the environment variables tab
6.) Copy the app name(the python app that was created in Heroku in Step-4 of the Deploy section) from the Heroku dashboard and paste it on the "value" text box of the environment variables tab
7.) Select the "master" branch from the "branches" filter. this ensures that the  CI/CD pipeline executes only when master branch is committed or merged.
8.) Run the CI/CD pipeline by clicking the specific repo on the circleci projects tab
9.) Observe the status tab for the CI/CD pipeline execution results
