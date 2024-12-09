---
title: "Tổng Quan Về CI/CD Pipeline"
date: "`r Sys.Date()`"
weight: 5
chapter: true
pre: "<b> 5 </b>"
---

## CI/CD Pipeline cho Triển Khai Tự Động

Trong phần này, chúng ta sẽ thiết lập một CI/CD (Continuous Integration and Continuous Deployment) pipeline sử dụng các dịch vụ của AWS như CodeCommit, CodePipeline, CodeBuild, và ECR. Pipeline này sẽ tự động hóa quá trình triển khai, đảm bảo các bản cập nhật mã được tích hợp, xây dựng và triển khai một cách hiệu quả vào môi trường container hóa trên AWS.

### Nội Dung

- **[5.1 - CodeCommit](5.1-CodeCommit/)**: Thiết lập repository trên CodeCommit để quản lý phiên bản mã.
- **[5.2 - CodePipeline](5.2-CodePipeline/)**: Tạo pipeline để tự động hóa quy trình CI/CD.
- **[5.3 - CodeBuild](5.3-CodeBuild/)**: Cấu hình môi trường build để biên dịch và đóng gói mã nguồn.
- **[5.4 - ECR](5.4-ECR/)**: Thiết lập Amazon ECR để lưu trữ Docker images.

Kết thúc phần này, bạn sẽ có một CI/CD pipeline hoạt động hoàn chỉnh có thể xử lý các bản cập nhật mã một cách tự động.