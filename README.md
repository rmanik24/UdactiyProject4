[![CircleCI](https://dl.circleci.com/status-badge/img/gh/rmanik24/UdactiyProject4/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/rmanik24/UdactiyProject4/tree/main)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

* Run `make lint` to run lint checks on the project code. If all requirements should be satisfied, and you should see a printed statement that rates your code like below
  Your code has been rated at 10.00/10

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh` 
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

### Explanation of files in the repository.
* Dockerfile - Docker can build images automatically by reading the instructions from a Dockerfile. The Dockerfile contains all the commands a user could call on the command line to assemble an image.
* run_docker.sh - In order to run a containerized application, you’ll need to build and run the docker image that you defined in the Dockerfile and then you should be able to test your application, locally, using run_docker.sh
* make_prediction.sh - To make a prediction, run make_prediction.sh that will send some input data to your containerized application and show the prediction outcome.
* upload_docker.sh - To upload an image to docker that we build already.
* run_kubernetes.sh - To deploy your application on the Kubernetes cluster using kubectl, which is a command line interface for interacting with Kubernetes clusters.
