[![CircleCI](https://circleci.com/gh/Remon222/project-4/tree/main.svg?style=svg)](https://circleci.com/gh/Remon222/project-4/tree/main)

# Project Overview

Deploy a containerized Python application to make a house price predictions. It uses a a pre-trained, sklearn model that has been trained to predict housing prices in Boston according to several features.

# Instructions on how to run the Python scripts and web app

- Create a virtualenv and activate it
	python3 -m venv .devops
	source .devops/bin/activate

- make install "To install all the requirements" 

-  install or make sure that you have installed
	Docker
	Hadolint and pylint    >>>> (try make lint to check that everything will pass )
	Kubernetes (Minikube & kubectl)
    

### To Run the App

1. Localy:  `python app.py`
2. Run in Docker container localy:  `./run_docker.sh`
3. Run in Kubernetes cluster localy:  `./run_kubernetes.sh`

# A short explanation of the files in the repository

.circleci/config.yml >> configuration file for the CI/CD pipeline containing the workflow jobs

output_txt_files >> contain the output logs of the python app when ran from localy containerized app and K8s cluster container.

app.py >> python app source code

Dockerfile >> Docker file contains info needed for building the container , such as the Base image.

make_prediction >> testing script sends request with needed payload to the running app 

Makefile >> file contains named groups of commands/steps can be ran by making the name of the group

requirements >> contain the 3rd party libraries/packages needed for the app and need to be packed up in the container with it

run_docker.sh >> script to build and run docker container

upload _docker >> to upload/push the builded image/container to docker hub

run _kubernates.sh >> script to run containers within a K8s cluster/pod