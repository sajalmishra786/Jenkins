CI/CD Pipeline with Jenkins and AWS
Overview
This repository contains scripts and configurations to set up a Continuous Integration (CI) pipeline using Jenkins and AWS EC2 instances. The pipeline fetches a sample project from GitHub, builds it using Maven, runs tests, performs code analysis with SonarQube, and uploads artifacts to NexusOSS.

Setup Instructions
Prerequisites
AWS account with permissions to create EC2 instances.
Basic understanding of Jenkins, Maven, SonarQube, and NexusOSS.
EC2 Instances Setup
Jenkins Instance:

Launch an EC2 instance with Jenkins installed. Follow the official Jenkins documentation for installation steps.
Install necessary plugins: Nexus Artifact Uploader, SonarQube Scanner, Pipeline Maven Integration, etc.
SonarQube Instance:

Launch an Ubuntu EC2 instance.
Install SonarQube, Nginx, and PostgreSQL according to the setup instructions.
Nexus Instance:

Launch a CentOS EC2 instance.
Install NexusOSS following the installation guide.
Jenkins Setup
Configure Jenkins:

Install Jenkins plugins required for the pipeline.
Set up Jenkins credentials for GitHub, NexusOSS, and SonarQube.
Create a Jenkins Pipeline:

Copy the Jenkinsfile from this repository into your Jenkins pipeline configuration.
Update the pipeline script as needed based on your environment settings.
Running the Pipeline
Fetch Code:

Jenkins pipeline will fetch code from the GitHub repository.
Build:

Maven will build the project, skipping tests during this phase.
Test:

Maven will run unit tests on the project.
Checkstyle Analysis:

Maven will perform Checkstyle analysis on the code.
Sonar Analysis:

SonarQube will analyze the code for quality metrics using the configured SonarQube server.
Quality Gate:

Jenkins will wait for the Quality Gate status from SonarQube.
Upload Artifact:

The pipeline will upload the built artifact (WAR file) to NexusOSS for artifact management.
Screenshots
![2024-06-10 (2)](https://github.com/sajalmishra786/Jenkins/assets/128459436/685fea8c-2a3d-4d40-bf72-196c4ca65f87)
![2024-06-10 (3)](https://github.com/sajalmishra786/Jenkins/assets/128459436/51f5bbfe-6797-4358-88ab-bbf70a06d6d9)
![2024-06-05](https://github.com/sajalmishra786/Jenkins/assets/128459436/c7a3bad2-703e-4686-905c-87e3d2ce7afc)
![2024-06-09](https://github.com/sajalmishra786/Jenkins/assets/128459436/c1459e1f-dcd0-4088-83e1-2db8b7307af4)
![2024-06-09 (1)](https://github.com/sajalmishra786/Jenkins/assets/128459436/d6460d17-9e37-48e3-b5c6-a2cd2e5f5124)
![2024-06-10](https://github.com/sajalmishra786/Jenkins/assets/128459436/7a0235b5-61a0-420e-8c36-644495535776)
![2024-06-10 (1)](https://github.com/sajalmishra786/Jenkins/assets/128459436/4d9f75b4-98d9-4ee8-b2db-b2d8a67ba2ee)
Contributing
Contributions are welcome! If you have suggestions or improvements, please fork the repository and create a pull request.

Credits
This project was developed as part of a DevOps course on Udemy, where I learned the foundational skills for setting up CI/CD pipelines.
