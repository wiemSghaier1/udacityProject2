[![Python application test with Github Actions](https://github.com/wiemSghaier1/udacityProject2/actions/workflows/pythonapp.yml/badge.svg)](https://github.com/wiemSghaier1/udacityProject2/actions/workflows/pythonapp.yml)


# Overview

This project employs an Agile methodology to develop and deploy a Flask-based application, leveraging GitHub Actions and Azure Pipelines for an efficient CI/CD workflow. The main components of the project are:

  * Version Control & Collaboration: GitHub Repository: Hosts the Flask starter code.
                                    GitHub Actions: Facilitates automated version control and seamless collaboration.
  * Continuous Deployment with Azure Pipelines: Azure Pipeline Deployment: An Azure pipeline automates the deployment of the application to an Azure Web App. It is configured to build and release updates with each code change, ensuring rapid iteration and deployment.
  * Self-Hosted Agent: The pipeline operates on a self-hosted agent, providing greater control over the build environment.
  * Prediction API Integration: After deployment, the application interacts with an API endpoint to fetch real-time predictions.
This project demonstrates the end-to-end development lifecycle, from coding and testing to deployment, highlighting how Agile practices and cloud-based CI/CD tools streamline modern software development.

## Project Plan
 Project Plan

* [A link to a Trello board for the project](https://trello.com/b/3O0o0gen/udacity)
* [A link to a spreadsheet that includes the original and final project plan](https://github.com/wiemSghaier1/udacityProject2/blob/main/project-management-template(Sheet1).csv)

## Instructions

 
![image](https://github.com/user-attachments/assets/6203b923-1dc8-44b4-8b01-8fd35b5e6c4b)


## Initial Setup

### Setting up a GitHub Repository
1. **Create a GitHub Repository:** This repository will store your source control.

### Configuring Azure Cloud Shell
1. **Launch Cloud Shell:**
   - From the Azure portal, click the Cloud Shell icon (top-right).

2. **Clone Project into Azure Cloud Shell:**
   - First, create an SSH key in your Cloud Shell to configure it to communicate with GitHub:
     ```sh
     ssh-keygen -t rsa
     ```
   - Copy the generated key and add it as a new SSH key in your GitHub account settings. This allows encrypted communication with GitHub and enables code checkout.

### Setting up the Development Environment
1. **Create and Launch a Virtual Environment:**
   - In your Cloud Shell, run the following command to create a virtual environment:
     ```sh
     python3 -m venv ~/.myrepo
     ```
   - Activate the virtual environment:
     ```sh
     source ~/.myrepo/bin/activate
     ```

2. **Clone the Repository into the Environment:**
   - Clone your repository:
     ```sh
     git clone <repository_url>
     ```
   - Navigate into the project folder:
     ```sh
     cd your-project
     ```
![gitclone](https://github.com/user-attachments/assets/3ef4b422-498f-46ca-b6de-9efef3d711b7)

### Passing Tests
1. **Run `make all`:**
   - This command will install dependencies, run linting, and execute tests.
     ```sh
     make all
     ```
![makeall](https://github.com/user-attachments/assets/6848a93c-5756-47dd-91e2-f2347c7aafe8)


## Setting up GitHub Actions

1. **Create a GitHub Action:**
   - In your project repository, go to the **Actions** tab.
   - Start setting up an action with the name `<name>.yml`.
   - Paste the script into the YAML file. Ensure the source branch is set to `main`.

2. **Verify Remote Test:**
   - Ensure that the remote test is passing.

![githubaction2](https://github.com/user-attachments/assets/35f823b4-a783-45ae-88e6-d0792fdfcc22)

## Project Running on Azure App Service

### Deploy the Project to Azure App Service
1. **Run the following command:**
   ```sh
   az webapp up --sku F1 -n <name> -g <resource group>
## Access the Application
Once deployed, open the displayed URL in your browser to see the running Python app.

## Setting up Azure Pipelines

### Successful Deployment in Azure Pipelines
1. **Refer to Official Documentation:** Always refer to and double-check the official documentation when setting up CI/CD.

### Create a New Project in Azure DevOps:
1. Go to the Azure DevOps portal and create a new project.
2. Allow the creation of public projects by turning on visibility in the Organization settings under the Policies section.

### Set Up a Service Connection:
1. Navigate to Project settings > Service connection.
2. Set up a connection via Azure Resource Manager and authenticate using a Service Principal.

### Create a Personal Access Token (PAT):
1. Go to your Azure DevOps home and click on Personal Access Tokens.
2. Create a new PAT with full access scope. This token will be used by the build agent for authentication.

### Add a Self-Hosted Agent Pool:
1. From Project settings, add a new self-hosted agent pool.
2. Grant access permission to all pipelines.

### Create an Agent (VM) in Azure Cloud Shell:
1. Go back to Azure Cloud Shell and create an agent (VM).
2. Perform all necessary configurations inside the VM to ensure the agent runs correctly.

![agentpool](https://github.com/user-attachments/assets/4b49c23b-5ee2-4cd8-9daf-707433cd9200)
#### Create Pipeline:
- In the YAML file, define the pipeline environment, stages, jobs, tasks, build agent, and other configurations to build the code from GitHub and deploy it to Azure services.

#### Add Stages to the Pipeline:
- **Build Stage:** Define the build process.
- **Deploy Web App:** Define the deployment process.

#### Successful Pipeline Deployment:
- At the end, ensure that the pipeline deployment is successful.

## Successful Prediction from Deployed Flask App in Azure Cloud Shell

Use this file as a template for the deployed prediction.

### Run Command
```bash
bash make_predict_azure_app.sh
![predection](https://github.com/user-attachments/assets/5df551e3-670b-476f-815e-efc6a7925782)

Output of streamed log files from deployed application
![streamlog](https://github.com/user-attachments/assets/2c732c95-5b9f-4911-b68b-e351faa277e7)


## Enhancements

## Improved CI/CD Pipeline
- Integrate automated testing with tools like Selenium for end-to-end testing.
- Add code quality checks using tools like SonarQube.

## Scalability
- Use Azure Kubernetes Service (AKS) for container orchestration.
- Implement auto-scaling for the web app to handle varying loads.

## Monitoring and Logging
- Integrate Azure Monitor and Application Insights for real-time monitoring and logging.
- Set up alerts for critical issues.

## Performance Optimization
- Use a Content Delivery Network (CDN) to improve load times.
- Optimize database queries and use caching mechanisms.

## User Interface Enhancements
- Improve the UI/UX design for better user experience.
- Add responsive design to support various devices.


## Demo 

[demo link Screencast on YouTube](https://youtu.be/2vv5tJ105Gs)


