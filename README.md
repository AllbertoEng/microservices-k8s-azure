# Deploying .Net Microservices to Azure Kubernetes Services(AKS) and Automating with Azure DevOps
Deploying .Net Microservices into Kubernetes, and moving deployments to the cloud Azure Kubernetes Services (AKS) with using Azure Container Registry (ACR) and Automating Deployments with Azure DevOps and GitHub.

| Image | Status |
| ------------- | ------------- |
| Shopping Client |  X |
| Shopping API | X | | |

### Overall Picture

![Overall Picture of Repository](https://user-images.githubusercontent.com/1147445/105671396-b152f580-5ef3-11eb-8f3b-7f9f7c9c4d24.png)

### Shopping MVC Client Application
The Shopping MVC Client Application was developed for consuming API resources, which became the Shopping.Client Asp.Net MVC Web Project. 
It started as a standalone Web application containing its own data. Container support was then added with a DockerFile, docker images were pushed to Docker Hub, 
and deployment options such as “Azure Web App for Container” resources for a single web application were explored.

### Shopping API Application
The Shopping.API Microservice was developed with MongoDb, and all Docker containers were composed.
This API project managed product data and performed CRUD operations by exposing API methods consumed by the Shopping Client project.
The API application was containerized by creating a DockerFile, and images were pushed to Azure Container Registry (ACR).

### Mongo Db
The API project managed product records stored in a NoSQL MongoDb database, as described in the diagram.
A MongoDb docker image was pulled from Docker Hub and a connection was established with the API project.
At the end of this section, there were 3 microservices: Shopping.Client — Shopping.API — MongoDb.
As can be seen:
Created docker images,
Composed docker containers and tested them,
Deployed these docker container images on local Kubernetes clusters,
Pushed images to ACR,
Shifted deployment to the cloud with Azure Kubernetes Services (AKS),
Updated microservices with zero-downtime deployments.

### Deploy to Azure Kubernetes Services (AKS) through CI/CD Azure Pipelines
The final step focused on automation of deployments by creating CI/CD pipelines in Azure DevOps. Separate microservices deployment pipeline YAMLs were developed using Azure Pipelines.
When code was pushed to GitHub, the microservices pipeline triggered, built docker images, pushed them to ACR, and deployed to Azure Kubernetes Services (AKS) with zero-downtime deployments.

![cicd](https://user-images.githubusercontent.com/1147445/105671542-f37c3700-5ef3-11eb-9532-59a5855214d0.png)
