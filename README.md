# Kidney Disease Classification Project

## Introduction

Welcome to the Kidney Disease Classification project! This project focuses on developing a deep learning model for classifying kidney diseases based on CT scans. The model is designed to categorize CT images into different classes such as Normal, Cyst, Tumor, and Stone.

## Resources
- [Readme](Readme.md)

## Workflows

### Steps to Run

1. **Clone the repository:**

    ```bash
    git clone https://github.com/krishnaik06/Kidney-Disease-Classification-Deep-Learning-Project
    ```

2. **Create a conda environment after opening the repository:**

    ```bash
    conda create -n cnncls python=3.8 -y
    conda activate cnncls
    ```

3. **Install the requirements:**

    ```bash
    pip install -r requirements.txt
    ```

4. **Run the application:**

    ```bash
    python app.py
    ```

5. **Open your local host and port.**

### MLflow

- MLflow tutorial: [MLflow Documentation](https://www.mlflow.org/docs/latest/tutorials-and-examples/tutorial.html)
- **Run MLflow UI:**

    ```bash
    mlflow ui
    ```

### DVC

- **DVC commands:**

    ```bash
    dvc init
    dvc repro
    dvc dag
    ```

## About MLflow & DVC

**MLflow:**
- Production-grade platform
- Trace all experiments
- Logging and tagging your models

**DVC:**
- Lightweight for POC
- Lightweight experiment tracker
- Can perform Orchestration (Creating Pipelines)

## AWS CI/CD Deployment with GitHub Actions

1. **Log in to AWS console.**
2. **Create IAM user for deployment with specific access:**
    - EC2 access: Virtual machine
    - ECR: Elastic Container registry to save your docker image in AWS

### Deployment Description

1. Build docker image of the source code.
2. Push your docker image to ECR.
3. Launch your EC2.
4. Pull your image from ECR in EC2.
5. Launch your docker image in EC2.

### Policy

1. AmazonEC2ContainerRegistryFullAccess
2. AmazonEC2FullAccess

### Steps for Deployment

1. Create ECR repo to store/save docker image. Save the URI: `566373416292.dkr.ecr.us-east-1.amazonaws.com/chicken`.
2. Create EC2 machine (Ubuntu).
3. Open EC2 and Install docker in EC2 Machine (optional and required steps provided).
4. Configure EC2 as self-hosted runner.
5. Setup GitHub secrets:

    ```plaintext
    AWS_ACCESS_KEY_ID=
    AWS_SECRET_ACCESS_KEY=
    AWS_REGION=us-east-1
    AWS_ECR_LOGIN_URI=demo>>566373416292.dkr.ecr.ap-south-1.amazonaws.com
    ECR_REPOSITORY_NAME=simple-app
    ```