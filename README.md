# PG DO - DevOps Certification Training - David Margolis

# Course 1

# Project 2 - Build a Docker Jenkins Pipeline to Implement CI/CD Workflow

## DESCRIPTION

Demonstrate the continuous integration and delivery by building a Docker Jenkins Pipeline.

## Problem Statement

You are a DevOps consultant in AchiStar Technologies. The company decided to implement DevOps to develop and deliver their products. Since it is an Agile organization, it follows Scrum methodology to develop the projects incrementally. You are working with multiple DevOps Engineers to build a Docker Jenkins Pipeline. During the sprint planning, you agreed to take the lead on this project and plan on the requirements, system configurations, and track the efficiency. The tasks you are responsible for:

- Availability of the application and its versions in the GitHub
  - Track their versions every time a code is committed to the repository
- Create a Docker Jenkins Pipeline that will create a Docker image from the Dockerfile and host it on Docker Hub
- It should also pull the Docker image and run it as a Docker container
- Build the Docker Jenkins Pipeline to demonstrate the continuous integration and continuous delivery workflow

Company goal is to deliver the product frequently to the production with high-end quality.

## You must use the following tools:

- Docker: To build the application from a Dockerfile and push it to Docker Hub
- Docker Hub: To store the Docker image
- GitHub: To store the application code and track its revisions
- Git: To connect and push files from the local system to GitHub
- Linux (Ubuntu): As a base operating system to start and execute the project
- Jenkins: To automate the deployment process during continuous integration

## Following requirements should be met:

- Document the step-by-step process from the initial installation to the final stage
- Track the versions of the code in the GitHub repository
- Availability of the application in the Docker Hub
- Track the build status of Jenkins for every increment of the project

# Solution

## Prerequisites:

Setup the following software on your machine:
- [Docker Desktop](https://docs.docker.com/desktop/windows/install/), and configure:
  - Check box for setting - Docker Desktop -> Settings -> General -> Use Docker Compose V2 
- git
    ```
    sudo apt-get install git
    ```
- jenkins
    ```
    wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add
    sudo bash -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
    sudo apt update
    sudo apt-get install jenkins
    ```

## Setting up Repo:

1. Create GitHub repo
1. Add [app.py](./app.py) and [requirements.txt](./requirements.txt) based on [Flask tutorial](https://flask.palletsprojects.com/en/2.0.x/quickstart/)
1. Add Dockerfile to create and run Flask application

## Running project locally

1. Build and run docker container:
    ```
    docker run -p 5000:5000 --rm -it $(docker build -q .)
    ```
1. Open app http://127.0.0.1:5000

## Running Jenkins

1. Run Jenkins
    ```
    sudo service jenkins start
    ```
1. Open jenkins http://localhost:8080/ and login

