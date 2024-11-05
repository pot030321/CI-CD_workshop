---
title: "Preparation Steps"
date: "2024-09-15"
weight: 2
chapter: false
pre: "<b>2.</b>"
---

{{% notice info %}}
To complete this workshop, you need a source repository on **AWS CodeCommit**, a CI/CD pipeline, and supporting AWS services to enable automation.
{{% /notice %}}

### Preparation Requirements

1. **Create a repository on CodeCommit**: This will be where the application source code is stored for automated build and deployment.
   - Go to the **AWS CodeCommit Console** and create a new repository.
   - See the detailed guide [here](https://docs.aws.amazon.com/codecommit/latest/userguide/getting-started.html).

2. **Configure IAM Role**: Create an IAM Role with the necessary permissions for CodePipeline, CodeBuild, ECS, and other services required for CI/CD.
   - Go to the **AWS IAM Console** and create an IAM Role with permissions for CodePipeline, CodeBuild, and ECS.
   - Ensure the role has access to S3 for storing build artifacts and logs.

3. **Set up ECR (Elastic Container Registry)**: Create a repository in ECR to store Docker images after they are built.
   - Go to the **AWS ECR Console** and create a new repository for your Docker images.
   
4. **Set up CodePipeline**: Create a pipeline to manage and automate the CI/CD process.
   - Go to the **AWS CodePipeline Console** and create a pipeline with the stages **Source (CodeCommit)**, **Build (CodeBuild)**, and **Deploy (ECS)**.
   - Ensure the pipeline is connected to CodeCommit for source, CodeBuild for build, and ECS for deployment.

5. **Configure CodeBuild**: Create a build project in CodeBuild to build and test the application.
   - Go to the **AWS CodeBuild Console** and create a new build project.
   - Use a `buildspec.yml` file to define build steps, push Docker image to ECR, and run tests (if necessary).

6. **Set up ECS (Elastic Container Service)**: Create an ECS Cluster and Task Definition to manage containers.
   - Go to the **AWS ECS Console**, create an ECS Cluster with Fargate or EC2.
   - Create a **Task Definition** for the container, specifying the Docker image from ECR.

7. **Set up Application Load Balancer (ALB)**: Create an ALB to distribute traffic to the application containers.
   - Go to the **AWS EC2 Console** and create an **Application Load Balancer** in the Public Subnet.
   - Link ALB with the ECS Service to distribute traffic.

8. **S3 Bucket (optional)**: If you need to store logs or artifacts from CodeBuild, create an S3 bucket.
   - Go to the **AWS S3 Console** and create a new bucket for storing logs and artifacts.

### Preparation Content
  - [Create a repository on CodeCommit](2.1-create-codecommit/)
  - [Configure IAM Role for CI/CD](2.2-configure-iam-role/)
  - [Set up ECR for Docker Images](2.3-setup-ecr/)
  - [Create pipeline in CodePipeline](2.4-setup-codepipeline/)
  - [Configure project in CodeBuild](2.5-configure-codebuild/)
  - [Set up ECS Cluster and Task Definition](2.6-setup-ecs/)
  - [Set up Application Load Balancer (ALB)](2.7-setup-alb/)
  - [Create S3 Bucket for logs and artifacts (optional)](2.8-create-s3-bucket/)
