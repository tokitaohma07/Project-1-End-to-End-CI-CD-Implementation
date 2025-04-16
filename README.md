# Project-01-End-to-End-CI-CD-Implementation

This project demonstrates an end-to-end Continuous Integration and Continuous Deployment (CI/CD) pipeline using a simple Python Flask web application. The application is containerized using Docker and integrated with a CI/CD pipeline that can be extended to Kubernetes and cloud platforms like AWS.

## 📁 Project Structure
├── Dockerfile # Docker configuration for building the app image ├── README.md # Project documentation ├── app.py # Flask application source code ├── requirements.txt # Python dependencies

Docker Setup

# Use official Python image as base
FROM python:3.9-slim

# Set work directory
WORKDIR /app

# Copy requirements and install
COPY requirements.txt .
RUN pip install -r requirements.txt

# Copy the rest of the app
COPY . .

# Expose the port and run the app
EXPOSE 5000
CMD ["python", "app.py"]


⚙️ CI/CD Pipeline Overview
You can use Jenkins to set up the CI/CD pipeline:

Pull Code from GitHub.

Build Docker Image using the Dockerfile.

Push Image to DockerHub or AWS ECR.

Deploy to Kubernetes cluster (EKS or local).
