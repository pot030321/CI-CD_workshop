---
title: "Load Balancer"
date: "`r Sys.Date()`"
weight: 2
chapter: true
pre: "<b>6.2 </b>"
---

Trong phần này, chúng ta sẽ thiết lập **Application Load Balancer (ALB)** để phân phối lưu lượng truy cập đến các container trong ECS Cluster. ALB giúp cải thiện khả năng chịu tải và đảm bảo độ tin cậy cho ứng dụng của bạn.

#### Bước 6.2.1: Tạo Application Load Balancer

1. Truy cập vào [EC2 Console](https://console.aws.amazon.com/ec2/v2/home).
   - Chọn **Load Balancers** và nhấp vào **Create Load Balancer**.

2. Chọn **Application Load Balancer** và cấu hình như sau:
   - **Tên**: Lab-ALB
   - **Scheme**: Internet-facing hoặc Internal
   - **IP address type**: IPv4
   - **VPC**: Chọn VPC mà ECS đang chạy trong đó.

3. Cấu hình Listener:
   - **Listener**: Cổng 80 hoặc 443 nếu muốn bảo mật SSL.
   - **Target Group**: Tạo Target Group cho các container trong ECS Cluster.

4. Nhấp **Create Load Balancer** để hoàn tất.

#### Bước 6.2.2: Liên kết ALB với ECS Service

1. Trong **ECS Console**, điều hướng đến **Clusters** và chọn **Lab-Cluster**.
   - Chọn **Services** và chỉnh sửa service muốn liên kết với ALB.

2. Cấu hình Service:
   - **Loại Load Balancer**: Application Load Balancer
   - **Target Group**: Chọn Target Group đã tạo từ ALB.

3. Nhấp **Update** để lưu thay đổi.
