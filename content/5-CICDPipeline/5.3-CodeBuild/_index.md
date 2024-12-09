---
title: "Create Build Project"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 5.3.1 </b> "
---

#### Create Build Project with CodeBuild

1. Go to the [CodeBuild service management console](https://console.aws.amazon.com/codebuild/home).
   - Click **Create build project**.
   - In **Project name**, enter the project name, e.g., `MyAppBuildProject`.

2. In the **Source** section, select **CodeCommit**.
   - Choose the repository you created in the CodeCommit section.

3. In the **Environment** section, select the operating system, runtime, and image that suit your project.
   - For example, choose **Cloud 9** and **Standard: 5.0**.

4. In **Buildspec**, choose **Insert build commands** or create a `buildspec.yml` file.

5. Click **Create build project** to complete.
