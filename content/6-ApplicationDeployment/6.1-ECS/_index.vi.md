---
title: "ECS"
date: "`r Sys.Date()`"
weight: 1
chapter: true
pre: "<b>6.1 </b>"
---

Phần này sẽ hướng dẫn bạn cấu hình **Amazon ECS** để triển khai ứng dụng container hóa. ECS cung cấp giải pháp quản lý container trên AWS, giúp ứng dụng của bạn dễ dàng mở rộng và an toàn hơn.

#### Bước 6.1.1: Tạo ECS Cluster

1. Truy cập vào [ECS Console](https://console.aws.amazon.com/ecs).
   - Chọn **Clusters** và nhấp vào **Create Cluster**.

2. Chọn loại cluster **Networking only** hoặc **EC2 Linux + Networking** nếu muốn chạy trên EC2.
   - Đặt tên cho cluster, ví dụ: **Lab-Cluster**.
   - Cấu hình VPC và subnet để ECS cluster hoạt động.

3. Nhấp **Create** để tạo ECS Cluster.
   - Kiểm tra xem cluster đã được tạo thành công.

#### Bước 6.1.2: Tạo Task Definition

1. Trong **ECS Console**, điều hướng đến **Task Definitions** và chọn **Create new Task Definition**.
   - Chọn **EC2** hoặc **Fargate** tùy thuộc vào cấu hình mong muốn.

2. Cấu hình Task Definition:
   - **Tên Task**: Đặt tên cho task (ví dụ: **Lab-Task**).
   - Thêm cài đặt cho container:
      + **Tên Container**: Lab-Container
      + **Image**: Docker image của ứng dụng (ví dụ, `nginx:latest`)
      + **Port mappings**: 80:80 (hoặc cổng mà ứng dụng sử dụng)

3. Cấu hình tài nguyên (CPU, memory) theo yêu cầu.
   - Nhấp **Create** để lưu Task Definition.

#### Bước 6.1.3: Chạy Task trên ECS

1. Trong **ECS Console**, điều hướng đến **Clusters** và chọn **Lab-Cluster**.
   - Chọn **Run Task** để khởi chạy task.

2. Cấu hình task:
   - **Launch type**: Chọn EC2 hoặc Fargate.
   - **Task Definition**: Chọn Task Definition đã tạo.

3. Nhấp **Run Task** để triển khai container trên ECS.
   - Kiểm tra xem task đã khởi chạy thành công.
