---
title: "Create ECR Repository"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 5.4.1 </b> "
---

#### Create ECR Repository

1. Go to the [ECR service management console](https://console.aws.amazon.com/ecr/home).
   - Click **Create repository**.
   - In **Repository name**, enter the repository name, e.g., `myapp-ecr-repo`.
   - Select additional options if needed, like scan on push for security checks on new images.

2. Click **Create repository** to complete.

3. Save the URI of the repository to use during the Docker image build and deploy process.
