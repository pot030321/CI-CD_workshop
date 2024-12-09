---
title: "Create Pipeline"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 5.2.1 </b> "
---

#### Create Pipeline with CodePipeline

1. Go to the [CodePipeline service management console](https://console.aws.amazon.com/codepipeline/home).
   - Click **Create pipeline**.
   - In **Pipeline name**, enter the pipeline name, e.g., `MyAppPipeline`.
   - In **Service role**, select **New service role** to create a new role, or **Existing service role** if you already have one.

2. Click **Next** to set up the Source stage.
   - Under **Source provider**, select **CodeCommit**.
   - Select the repository and branch you created in the CodeCommit step.
   - Click **Next**.

3. Configure the Build stage.
   - Under **Build provider**, select **CodeBuild**.
   - Choose the project you created in the CodeBuild step.

4. Configure the Deploy stage.
   - Select **ECS** or **S3**, depending on your application type.

5. Click **Create pipeline** to complete.
