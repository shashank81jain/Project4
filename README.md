# Project4
[![CircleCI](https://circleci.com/gh/shashank81jain/Project4/tree/main.svg?style=svg)](https://circleci.com/gh/shashank81jain/Project4/tree/main)

# Project overview
Overview In this project a Machine Learning Microservice API is operationalized.

Given a pre-trained, sklearn model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on the data source site. This project tests your ability to operationalize a Python flask app—in a provided file, app.py—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

Project Tasks Project goal is to operationalize this working, machine learning microservice using kubernetes, which is an open-source system for automating the management of containerized applications. Below are the steps perfromed

*Testing project code using linting *Containerize this application using Docker *Deploy your containerized application using Docker and make a prediction *Improve the log statements in the source code for this application *Configure Kubernetes and create a Kubernetes cluster *Deploy a container using Kubernetes and make a prediction *Upload a complete Github repo with CircleCI to indicate that your code has been tested

# Setup the Environment

python3 -m venv ~/.devopsproj

source ~/.devopsproj/bin/activate

make install

make lint

# Running app.py
  Standalone: python app.py
  Run in Docker: ./run_docker.sh
  Run in Kubernetes: ./run_kubernetes.sh

# Kubernetes Steps
  Used Docker via Cloud9
  Setup and Configure Kubernetes locally
  Create Flask app in Container
  Run via kubectl

# Project Files and Details:
Project folder contains files that are required to create docker container,kubernetes pod and all plugins required for installation. LEts take a look at the files,
  app.py - its the main python application file.
  Makefile - its a make file to be used for the project setup and running in the environment. ensure the Make is installed. if windows machine is used, please install using      scoop.
  Dockerfile - this is main docker file , has key information for creating ikage and running it.
  requirement.txt - this is immportant file, given as input to Makefile. sometimes you may face issue with the plugins, so take a look at this and ensure that you have proper     version of plugin relvant to python3.7.
  run_docker.sh,run_kubernetes.sh - shell script to run docker and kubernetes command. the run kubernetes command might had to be run few times, as the pod creation will happen   in background. Fetch the kubernetes pod running status, if the pod is running then execute run_kubernetes.sh again to make the port in listening pode.
  upload_docker.sh - the shell script is used to upload the docker image creating using run_docker.sh. when this is executed you will be prompted to enter password. Please loginto dockerhub to confirm the docker image is uploaded. This is important because the run_kubernetes script will pull the docker image from the dockerhub only.
  make_prediction.sh - its a prediction input script, run it when the docker and kubernetes are running the app to get the output.
  .circleci/config.yml - its the circle configuration file to support devops deployement.
