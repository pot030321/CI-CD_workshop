---
title: "Tạo Pipeline"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 5.2.1 </b> "
---

#### Tạo Pipeline với CodePipeline

1. Truy cập vào [giao diện quản trị dịch vụ CodePipeline](https://console.aws.amazon.com/codepipeline/home).
   - Nhấn **Create pipeline**.
   - Trong **Pipeline name**, nhập tên pipeline, ví dụ: `MyAppPipeline`.
   - Trong **Service role**, chọn **New service role** để tạo vai trò mới hoặc **Existing service role** nếu bạn đã có vai trò.

2. Nhấn **Next** để thiết lập Source stage.
   - Ở mục **Source provider**, chọn **CodeCommit**.
   - Chọn repository và branch mà bạn đã tạo ở bước CodeCommit.
   - Nhấn **Next**.

3. Thiết lập Build stage.
   - Ở mục **Build provider**, chọn **CodeBuild**.
   - Chọn Project bạn đã tạo ở bước CodeBuild.

4. Thiết lập Deploy stage.
   - Chọn **ECS** hoặc **S3** tùy thuộc vào loại ứng dụng của bạn.

5. Nhấn **Create pipeline** để hoàn tất.
