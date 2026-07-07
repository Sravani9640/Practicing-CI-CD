# End-to-End CI/CD Pipeline using Azure DevOps, GitHub & AWS EC2

## Project Overview

This project demonstrates an end-to-end Continuous Integration and Continuous Deployment (CI/CD) pipeline using Azure DevOps, GitHub, a Self-Hosted Agent, and AWS EC2.

Whenever changes are pushed to the `main` branch of the GitHub repository, Azure DevOps automatically triggers the pipeline. The pipeline validates the source code, connects securely to an AWS EC2 instance using SSH, copies the website files using SCP, and deploys the application to the Nginx web server.

---

## Architecture

```
Developer
    │
    ▼
GitHub Repository
    │
    ▼
Azure DevOps Pipeline
    │
    ▼
Self-Hosted Agent (Windows)
    │
    ▼
Build & Validation Stage
    │
    ▼
Deploy Stage
    │
    ▼
AWS EC2 (Amazon Linux)
    │
    ▼
Nginx Web Server
    │
    ▼
Website
```

---

## Technologies Used

| Technology | Purpose |
|------------|---------|
| Azure DevOps | CI/CD Pipeline |
| GitHub | Source Code Management |
| YAML | Pipeline as Code |
| Self-Hosted Agent | Pipeline Execution |
| AWS EC2 | Application Hosting |
| Amazon Linux | Operating System |
| Nginx | Web Server |
| SSH | Secure Remote Access |
| SCP | Secure File Transfer |
| HTML/CSS | Sample Website |

---

## Pipeline Workflow

### Stage 1 – Build & Validation

- Checkout source code from GitHub
- Verify repository files
- Validate application files
- Test SSH connectivity to EC2

### Stage 2 – Deploy

- Copy website files to EC2 using SCP
- Deploy website to Nginx web directory
- Complete deployment

---

## Azure DevOps Pipeline

The pipeline is configured to trigger automatically whenever code is pushed to the **main** branch.

### Pipeline Stages

### Build

- Checkout Repository
- Verify Files
- Validate Application
- Test SSH Connectivity

### Deploy

- Copy Website to EC2
- Deploy to Nginx
- Deployment Successful

---

## Variable Group

A Variable Group named **First AWS-Deployment** is used to avoid hardcoding environment-specific values.

| Variable | Description |
|----------|-------------|
| EC2_IP | EC2 Public IP Address |
| EC2_USER | Linux Username |
| WEB_PATH | Nginx Web Root |

---

## Self-Hosted Agent

A Windows Self-Hosted Agent is configured to execute the Azure DevOps pipeline.

Advantages:

- No Microsoft-hosted parallelism limitations
- Faster execution
- Full control over the execution environment

---

## Deployment Process

1. Developer pushes code to GitHub.
2. Azure DevOps triggers the pipeline.
3. Self-hosted agent downloads the latest source code.
4. Pipeline validates required files.
5. SSH connectivity to EC2 is verified.
6. Website files are copied securely using SCP.
7. Files are deployed to the Nginx web root.
8. Website is updated successfully.

---

## Project Structure

```
AzureDevOps-AWS-CICD/
│
├── index.html
├── azure-pipelines.yml
├── README.md

```

---

## Challenges Faced

During the implementation of this project, several challenges were encountered and resolved.

- Azure DevOps hosted agent parallelism limitation
- Configured a Windows Self-Hosted Agent
- SSH private key permission issues
- AWS Security Group configuration
- Self-hosted agent offline troubleshooting
- Secure deployment using SSH and SCP

---

## Learning Outcomes

Through this project, I gained hands-on experience with:

- Azure DevOps YAML Pipelines
- GitHub Integration
- Self-Hosted Agents
- AWS EC2
- Linux Commands
- SSH & SCP
- Nginx Configuration
- Variable Groups
- CI/CD Best Practices
- Automated Application Deployment

---


---

## Author

**Sravani Punnam**

Application Support Engineer | Azure DevOps | AWS | DevOps Enthusiast
