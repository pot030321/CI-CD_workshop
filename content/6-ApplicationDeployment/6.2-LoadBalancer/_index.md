---
title: "Load Balancer"
date: "`r Sys.Date()`"
weight: 2
chapter: true
pre: "<b>6.2 </b>"
---

In this section, we will configure an **Application Load Balancer (ALB)** to distribute traffic to containers in the ECS Cluster. ALB enhances load distribution and reliability for your application.

#### Step 6.2.1: Create Application Load Balancer

1. Go to the [EC2 Console](https://console.aws.amazon.com/ec2/v2/home).
   - Select **Load Balancers** and click **Create Load Balancer**.

2. Choose **Application Load Balancer** and configure as follows:
   - **Name**: Lab-ALB
   - **Scheme**: Internet-facing or Internal
   - **IP address type**: IPv4
   - **VPC**: Select the VPC where ECS is running.

3. Configure Listener:
   - **Listener**: Port 80 or 443 for SSL.
   - **Target Group**: Create Target Group for ECS containers.

4. Click **Create Load Balancer** to finalize.

#### Step 6.2.2: Attach ALB to ECS Service

1. In **ECS Console**, navigate to **Clusters** and select **Lab-Cluster**.
   - Select **Services** and edit the service you wish to attach to ALB.

2. Configure Service:
   - **Load balancer type**: Application Load Balancer
   - **Target Group**: Select the Target Group created for ALB.

3. Click **Update** to save changes.
