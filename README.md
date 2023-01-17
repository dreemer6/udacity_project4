
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

* Create a virtualenv and activate it
Due to python3.7 are no longer availble in the installation packages, I used conda to create virtual enrinmrenet because I can still install python3.7 with conda.  I have miniconda3 installed on my local computer
* Run `source ~/miniconda3/bin/activate` to activate conda 
* Run `conda create -n .devops python=3.7` to create virtual env with python3.7 installed 
* Run `conda activate .devops` to activate venv `.devops`
* Run `make install` to install the necessary dependencies
* Run `make lint`  (pylint app.py files and hadolint Dockerfile) to detect errors in the code.  
* can also run `make all` instead of previous two steps.  

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`   
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

1. Setup and Configure Docker locally
    * install docker as described in the [link](https://docs.docker.com/engine/install/ubuntu/).
    * Run `./run_docker.sh`
    * Run `docker ps` to check if docker is running.
    * Run `./make_prediction.sh` to make prediction and copy/paste the logging info at terminal to `output_txt_files/docker_out.txt`
2. Setup and Configure Kubernetes locally
    * Run `curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`
    * Run `sudo install minikube-linux-amd64 /usr/local/bin/minikube`
    * Run `minikube start` to start minikube
    * Run `kubectl get pods` to see which pods are running.
    * Run `./run_kubernetes.sh`
    * Run `./make_prediction.sh` to make prediction and copy/paste the logging info at terminal to `output_txt_files/kubernetes_out.txt`
3. Create Flask app in Container
    * Run `./run_docker.sh` to build and start the Flask app container. 
    * Run `./upload_docker.sh` to upload the container to docker hub.   

