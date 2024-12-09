---
title: "ECS"
date: "`r Sys.Date()`"
weight: 1
chapter: true
pre: "<b>6.1 </b>"
---

In this section, we will configure **Amazon ECS** to deploy a containerized application. ECS provides a container management solution on AWS, making your application more scalable and secure.

#### Step 6.1.1: Create ECS Cluster

1. Go to the [ECS Console](https://console.aws.amazon.com/ecs).
   - Select **Clusters** and click **Create Cluster**.

2. Choose the **Networking only** cluster type or **EC2 Linux + Networking** if you want to run on EC2.
   - Name the cluster, e.g., **Lab-Cluster**.
   - Configure VPC and subnets for the ECS cluster to operate.

3. Click **Create** to create the ECS Cluster.
   - Verify that the cluster was successfully created.

#### Step 6.1.2: Create Task Definition

1. In the **ECS Console**, go to **Task Definitions** and select **Create new Task Definition**.
   - Choose **EC2** or **Fargate** depending on your setup.

2. Configure Task Definition:
   - **Task name**: Name the task (e.g., **Lab-Task**).
   - Add container settings:
      + **Container name**: Lab-Container
      + **Image**: The Docker image (e.g., `nginx:latest`)
      + **Port mappings**: 80:80 (or the required port)

3. Configure resources (CPU, memory) as required.
   - Click **Create** to save the Task Definition.

#### Step 6.1.3: Run Task on ECS

1. In the **ECS Console**, go to **Clusters** and select **Lab-Cluster**.
   - Click **Run Task** to start the task.

2. Configure the task settings:
   - **Launch type**: Select EC2 or Fargate.
   - **Task Definition**: Choose the created Task Definition.

3. Click **Run Task** to deploy the container on ECS.
   - Verify the task has started successfully.
