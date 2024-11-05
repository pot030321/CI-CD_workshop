---
title: "Các bước chuẩn bị"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: "<b>2.</b>"
---

{{% notice info %}}
Để thực hiện workshop này, bạn cần có một repository lưu trữ mã nguồn trên **AWS CodeCommit**, thiết lập pipeline CI/CD, và các dịch vụ hỗ trợ khác trên AWS để triển khai tự động hóa.
{{% /notice %}}

### Yêu cầu chuẩn bị trước

1. **Tạo repository trên CodeCommit**: Đây sẽ là nơi lưu trữ mã nguồn của ứng dụng mà chúng ta sẽ tự động hóa quá trình build và triển khai.
   - Truy cập **AWS CodeCommit Console** và tạo một repository mới.
   - Tham khảo hướng dẫn chi tiết [tại đây](https://docs.aws.amazon.com/codecommit/latest/userguide/getting-started.html).

2. **Cấu hình IAM Role**: Tạo IAM Role có các quyền cần thiết cho CodePipeline, CodeBuild, ECS, và các dịch vụ khác để thực hiện CI/CD.
   - Truy cập **AWS IAM Console** và tạo IAM Role với quyền cho CodePipeline, CodeBuild, và ECS.
   - Đảm bảo role có quyền truy cập vào S3 để lưu trữ artifacts và logs từ quá trình build.

3. **Thiết lập ECR (Elastic Container Registry)**: Tạo repository trên ECR để lưu trữ Docker images sau khi được build.
   - Truy cập **AWS ECR Console** và tạo một repository mới cho Docker images của bạn.
   
4. **Thiết lập CodePipeline**: Tạo pipeline để quản lý và tự động hóa quy trình CI/CD.
   - Truy cập **AWS CodePipeline Console** và tạo pipeline với các bước **Source (CodeCommit)**, **Build (CodeBuild)**, và **Deploy (ECS)**.
   - Đảm bảo pipeline được liên kết với CodeCommit và CodeBuild cho quy trình build, và ECS cho quy trình triển khai.

5. **Cấu hình CodeBuild**: Tạo project trong CodeBuild để thực hiện build và kiểm thử ứng dụng.
   - Truy cập **AWS CodeBuild Console** và tạo build project mới.
   - Sử dụng file `buildspec.yml` để cấu hình các bước build, push Docker image lên ECR, và kiểm thử (nếu cần).

6. **Thiết lập ECS (Elastic Container Service)**: Tạo ECS Cluster và Task Definition để quản lý các container.
   - Truy cập **AWS ECS Console**, tạo ECS Cluster với Fargate hoặc EC2.
   - Tạo **Task Definition** cho container, với Docker image từ ECR.

7. **Thiết lập Application Load Balancer (ALB)**: Tạo ALB để phân phối lưu lượng đến các container ứng dụng.
   - Truy cập **AWS EC2 Console** và tạo **Application Load Balancer** trong Public Subnet.
   - Liên kết ALB với ECS Service để phân phối traffic.

8. **S3 Bucket (tuỳ chọn)**: Nếu cần lưu trữ logs hoặc artifacts từ CodeBuild, tạo bucket S3.
   - Truy cập **AWS S3 Console** và tạo bucket mới để lưu trữ logs và artifacts.

### Nội dung chuẩn bị
  - [Tạo repository trên CodeCommit](2.1-create-codecommit/)
  - [Cấu hình IAM Role cho CI/CD](2.2-configure-iam-role/)
  - [Thiết lập ECR cho Docker Images](2.3-setup-ecr/)
  - [Tạo pipeline trong CodePipeline](2.4-setup-codepipeline/)
  - [Cấu hình project trong CodeBuild](2.5-configure-codebuild/)
  - [Thiết lập ECS Cluster và Task Definition](2.6-setup-ecs/)
  - [Thiết lập Application Load Balancer (ALB)](2.7-setup-alb/)
  - [Tạo S3 Bucket cho logs và artifacts (tuỳ chọn)](2.8-create-s3-bucket/)
