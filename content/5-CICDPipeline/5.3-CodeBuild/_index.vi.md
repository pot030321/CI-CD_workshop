---
title: "Tạo Build Project"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 5.3.1 </b> "
---

#### Tạo Build Project với CodeBuild

1. Truy cập vào [giao diện quản trị dịch vụ CodeBuild](https://console.aws.amazon.com/codebuild/home).
   - Nhấn **Create build project**.
   - Trong **Project name**, nhập tên project, ví dụ: `MyAppBuildProject`.

2. Tại mục **Source**, chọn **CodeCommit**.
   - Chọn repository mà bạn đã tạo ở phần CodeCommit.

3. Tại **Environment**, chọn hệ điều hành, runtime, và image phù hợp với dự án của bạn.
   - Ví dụ: chọn **Cloud 9** và **Standard: 5.0**.

4. Tại **Buildspec**, chọn **Insert build commands** hoặc tạo file `buildspec.yml`.

5. Nhấn **Create build project** để hoàn tất.
