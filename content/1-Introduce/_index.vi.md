---
title: "Giới thiệu về Tạo pipeline CI/CD trên AWS"
date: "2024-09-15"
weight: 1
chapter: true
pre: "<b>1</b>"
---

#### Workshop: Tạo pipeline tự động hóa xây dựng, kiểm thử, và triển khai ứng dụng trên AWS

Trong workshop này, chúng ta sẽ học cách sử dụng các dịch vụ AWS để xây dựng và triển khai một pipeline CI/CD hoàn chỉnh. Mục tiêu là tự động hóa quá trình xây dựng, kiểm thử và triển khai một ứng dụng web hoặc container mà không cần phát triển trên máy cục bộ.

### Các dịch vụ AWS cần thiết cho workshop này:

1. **CodeCommit**: Dịch vụ lưu trữ mã nguồn giúp quản lý và chia sẻ mã ứng dụng.
2. **CodePipeline**: Tự động hóa luồng công việc CI/CD, giúp triển khai mã nguồn từ CodeCommit qua các bước build, kiểm thử và triển khai.
3. **CodeBuild**: Xây dựng và kiểm thử mã nguồn từ CodeCommit, cho phép tạo Docker image và push lên ECR.
4. **ECR (Elastic Container Registry)**: Kho lưu trữ Docker image, nơi chứa các bản build của ứng dụng.
5. **ECS (Elastic Container Service)**: Chạy và quản lý container trên hạ tầng AWS, giúp triển khai ứng dụng dễ dàng với Fargate.
6. **ALB (Application Load Balancer)**: Phân phối lưu lượng truy cập tới các container ứng dụng, đảm bảo khả năng mở rộng và ổn định cho dịch vụ.
7. **IAM (Identity and Access Management)**: Quản lý quyền truy cập và cấp quyền cho các dịch vụ như CodePipeline, CodeBuild và ECS để đảm bảo an toàn và hiệu quả.
8. **S3 (Simple Storage Service)**: Lưu trữ các artifacts hoặc log từ CodeBuild, giúp theo dõi và phân tích quá trình build.

### Kế hoạch workshop:

Trong suốt workshop, bạn sẽ từng bước:
- Thiết lập **CodeCommit** để lưu trữ mã nguồn của ứng dụng.
- Cấu hình **CodePipeline** để tự động hóa quá trình CI/CD.
- Sử dụng **CodeBuild** để xây dựng Docker image và push lên **ECR**.
- Triển khai ứng dụng container trên **ECS** với **Application Load Balancer**.
- Sử dụng **IAM** để quản lý quyền truy cập an toàn cho các dịch vụ AWS.
- Lưu trữ log và artifacts trong **S3** để kiểm tra và phân tích.

Bây giờ, hãy bắt đầu với từng bước chi tiết để thiết lập pipeline CI/CD trên AWS!
