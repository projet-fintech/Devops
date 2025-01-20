# DevOps Pipeline Documentation


![image(5)](https://github.com/user-attachments/assets/149618a5-4f14-4e69-af84-a5c73d3e1e61)

## Overview
This repository contains the configuration and scripts to manage the CI/CD pipelines for a cloud-native FinTech application. The pipelines are designed to automate the build, test, and deployment processes for microservices and predictive models.

---

## Master Pipeline: `master-pipelines`

![MASTER_ORCHESTRATION drawio(2)](https://github.com/user-attachments/assets/a7efd334-ee7e-4ebc-ac00-b68016e15980)

The `master-pipelines` job orchestrates the CI/CD pipelines for all microservices and machine learning models. Each job within the pipeline consists of the following stages:

### **Pipeline Stages**
1. **Checkout**
   - Retrieves the source code from the Git repository.
   - Ensures the pipeline uses the latest version of the code.

2. **Build**
   - Compiles the source code for the respective service or model.
   - Verifies successful compilation before proceeding.

3. **Test**
   - Executes unit and integration tests.
   - Ensures code correctness and stability.

4. **SonarQube Analysis**
   - Runs static code analysis using SonarQube.
   - Displays detailed code quality reports (e.g., code smells, vulnerabilities, coverage).

5. **Build Docker Image**
   - Creates a Docker image for the service or model.
   - Tags the image with the appropriate version.

6. **Push Image to ECR**
   - Pushes the Docker image to AWS Elastic Container Registry (ECR).
   - Ensures the image is ready for deployment.

7. **Deploy Image to EKS**
   - Deploys the Docker image to an AWS EKS cluster.
   - Uses Kubernetes manifests or Helm charts for deployment.

8. **Cleanup Images from Local**
   - Removes local Docker images to free up disk space.

![PIPELINES drawio(1)](https://github.com/user-attachments/assets/698f8513-ac63-4af7-a2fa-dfd6037e1266)

---

## Features
- **Orchestration**: The `master-pipelines` job coordinates all services and models, ensuring seamless integration.
- **Code Quality Analysis**: Provides detailed SonarQube reports to maintain high standards.
- **Artifact Management**: Docker images are built, tagged, and stored in AWS ECR.
- **Scalable Deployment**: Services and models are deployed to Kubernetes (AWS EKS), ensuring scalability and reliability.
- **Pipeline Visualization**: Displays real-time progress and logs for each stage in the pipeline.

---

## Usage

### Prerequisites
- Jenkins  setup.
- Access to AWS ECR and EKS.
- SonarQube server configured for static code analysis.

### Running the Pipeline
1. Trigger the `master-pipelines` job from the CI/CD tool.
2. Monitor the progress through the pipeline dashboard.
3. Review SonarQube reports for code quality.
4. Verify deployment status in AWS EKS.

---

## Visualizations

### **SonarQube Reports**
- Accessible through the pipeline dashboard or SonarQube server.
- Key metrics:
  - Code coverage
  - Bugs and vulnerabilities
  - Code smells


![image](https://github.com/user-attachments/assets/4c3023fc-cd1d-4d48-b26b-d22c9903ef0a)

![image](https://github.com/user-attachments/assets/dd8d4391-6a91-4447-a524-f7d0b48d927e)

![image](https://github.com/user-attachments/assets/653ff95c-8a80-4805-ae9b-0a461ae0914e)

![image](https://github.com/user-attachments/assets/adc5097e-4c61-4e0c-a221-8ff1c90d7742)


### **Pipeline Logs**
- Real-time logs are available for each stage of the pipeline.
- Useful for debugging and performance monitoring.
  
  ![Uploading image.png…]()


---

## Tools and Technologies

### **CI/CD**
- Jenkins 

### **Static Code Analysis**
- SonarQube

### **Containerization**
- Docker

### **Cloud Services**
- AWS ECR
- AWS EKS

### **Orchestration**
- Kubernetes

---

## Contact
For support or inquiries, please contact [mouadrguibi900@gmail.com(mailto:mouadrguibi900@gmail.com).

---

## License
This repository is licensed under the MIT License.

