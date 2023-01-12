
# Operationalizing a Machine Learning Microservice API

[![CircleCI](https://dl.circleci.com/status-badge/img/gh/dreemer6/udacity_project4/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/dreemer6/udacity_project4/tree/main)

## Project Overview

This project operationalizes a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. The model is operationalized using a Python Flask app, available in `app.py`—that serves out predictions (inference) about housing prices through API calls via a microservice architecture using a Docker container and Kubernetes.

### Project Tasks

In this project, I:
* Tested my project code locally using linting
* Created a Dockerfile to containerize this application
* Deploy the containerized application using Docker and made a prediction
* Configured Kubernetes and created a Kubernetes cluster using minikube
* Deployed a container using Kubernetes and made a prediction
* Used CircleCI (`.circleci/config.yml`) to build a CI/CD pipeline that includes tests for the application code

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it.
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
Alternatively, run `make setup` to create and source the virtual environment

* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
