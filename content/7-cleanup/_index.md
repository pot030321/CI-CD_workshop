---
title: "Cleanup"
date: "`r Sys.Date()`"
weight: 7
chapter: true
pre: "<b>7 </b>"
---

In this section, we will go through the detailed steps to clean up each resource we created in this workshop. This is essential to avoid any ongoing charges on your AWS account.

### 1. Delete ECS Services and Cluster

1. Go to the [ECS Console](https://console.aws.amazon.com/ecs).
2. In the left menu, select **Clusters**.
3. Choose the **Cluster** you created for this workshop (e.g., **LabCluster**).
4. Select the **Services** tab and:
   - Click on each service.
   - Select **Update** and set **Desired tasks** to **0** to stop the service.
   - After the service stops, click **Delete** and confirm deletion.
5. Once all services are deleted, return to the **Cluster** list.
6. Select the cluster and click **Delete Cluster** to remove it completely.

### 2. Delete Application Load Balancer (ALB)

1. Go to the [EC2 Console](https://console.aws.amazon.com/ec2).
2. In the left menu, click **Load Balancers**.
3. Select the **Application Load Balancer** created for this workshop (e.g., **LabALB**).
4. Click **Actions > Delete** and confirm deletion.

### 3. Delete Auto Scaling Groups

1. In the **EC2 Console**, go to **Auto Scaling Groups** in the left menu.
2. Locate the **Auto Scaling Group** associated with your ECS cluster.
3. Select it, click **Delete**, and confirm the deletion.

### 4. Delete Elastic Container Registry (ECR) Repositories

1. Go to the [ECR Console](https://console.aws.amazon.com/ecr).
2. Select **Repositories** from the left menu.
3. Click on the repository you created (e.g., **LabRepo**).
4. Choose **View push commands** to ensure no images remain (optional).
5. Select **Delete** and confirm to delete the repository and its contents.

### 5. Delete S3 Buckets

1. Go to the [S3 Console](https://console.aws.amazon.com/s3).
2. Locate each **Bucket** you created for this workshop (e.g., **LabBucket**).
3. Click on the bucket name.
4. In the **Objects** tab, select **Empty bucket** to remove contents.
5. After the bucket is empty, go back to the **Buckets** view.
6. Select the bucket, click **Delete bucket**, and confirm deletion.

### 6. Remove IAM Roles and Policies

1. Go to the [IAM Console](https://console.aws.amazon.com/iam).
2. In the left menu, click **Roles**.
3. Search for roles you created (e.g., **LabRole** or **SSM-Role**).
4. Click on each role, and in the **Permissions** tab, detach policies associated with it (e.g., **AmazonSSMFullAccess**).
5. Return to the **Roles** list, select the role, and click **Delete Role** to remove it.
6. Repeat the same for any custom **Policies** created if necessary.

### 7. Delete VPC and Networking Components

1. Go to the [VPC Console](https://console.aws.amazon.com/vpc).
2. In the **Your VPCs** section:
   - Select the VPC you created (e.g., **LabVPC**).
   - Click **Actions > Delete VPC** and confirm.
3. For each **Subnet** created:
   - Go to **Subnets** in the left menu.
   - Select each subnet associated with **LabVPC** and click **Delete**.
4. Go to **Route Tables** and:
   - Delete any route tables associated with **LabVPC**.
5. Go to **Internet Gateways**:
   - Detach the gateway from **LabVPC** if attached.
   - Select the gateway and click **Delete Internet Gateway**.

### 8. Terminate EC2 Instances

1. Go to the [EC2 Console](https://console.aws.amazon.com/ec2).
2. In the **Instances** section:
   - Select the **Public** and **Private** instances created for the workshop.
   - Click **Actions > Instance State > Terminate**.
   - Confirm termination.

---