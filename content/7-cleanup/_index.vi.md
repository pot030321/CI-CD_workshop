---
title: "Dọn dẹp"
date: "`r Sys.Date()`"
weight: 7
chapter: true
pre: "<b>7 </b>"
---

Trong phần này, chúng tôi sẽ hướng dẫn chi tiết từng bước để dọn dẹp các tài nguyên đã tạo trong workshop này, giúp tránh các chi phí không cần thiết.

### 1. Xóa Dịch vụ và Cluster ECS

1. Truy cập [ECS Console](https://console.aws.amazon.com/ecs).
2. Trong menu bên trái, chọn **Clusters**.
3. Chọn **Cluster** bạn đã tạo cho workshop (ví dụ, **LabCluster**).
4. Chọn tab **Services** và:
   - Click vào từng dịch vụ.
   - Chọn **Update** và đặt **Desired tasks** là **0** để dừng dịch vụ.
   - Sau khi dịch vụ dừng, click **Delete** và xác nhận xóa.
5. Sau khi xóa hết dịch vụ, quay lại danh sách **Cluster**.
6. Chọn cluster và click **Delete Cluster** để xóa hoàn toàn.

### 2. Xóa Application Load Balancer (ALB)

1. Truy cập [EC2 Console](https://console.aws.amazon.com/ec2).
2. Trong menu bên trái, chọn **Load Balancers**.
3. Chọn **Application Load Balancer** đã tạo cho workshop (ví dụ, **LabALB**).
4. Click **Actions > Delete** và xác nhận xóa.

### 3. Xóa Auto Scaling Groups

1. Trong **EC2 Console**, chọn **Auto Scaling Groups** từ menu bên trái.
2. Tìm **Auto Scaling Group** liên quan đến cluster ECS của bạn.
3. Chọn nó, click **Delete** và xác nhận xóa.

### 4. Xóa Elastic Container Registry (ECR) Repositories

1. Truy cập [ECR Console](https://console.aws.amazon.com/ecr).
2. Chọn **Repositories** từ menu bên trái.
3. Click vào repository bạn đã tạo (ví dụ, **LabRepo**).
4. Chọn **Delete** và xác nhận xóa repository cùng với nội dung.

### 5. Xóa S3 Buckets

1. Truy cập [S3 Console](https://console.aws.amazon.com/s3).
2. Tìm **Bucket** đã tạo cho workshop (ví dụ, **LabBucket**).
3. Click vào tên bucket.
4. Trong tab **Objects**, chọn **Empty bucket** để xóa nội dung.
5. Quay lại giao diện **Buckets**.
6. Chọn bucket, click **Delete bucket** và xác nhận xóa.

### 6. Xóa IAM Roles và Policies

1. Truy cập [IAM Console](https://console.aws.amazon.com/iam).
2. Trong menu bên trái, chọn **Roles**.
3. Tìm các role đã tạo (ví dụ, **LabRole** hoặc **SSM-Role**).
4. Click vào từng role và trong tab **Permissions**, hủy gán các policy liên quan (ví dụ, **AmazonSSMFullAccess**).
5. Quay lại danh sách **Roles**, chọn role và click **Delete Role** để xóa.
6. Lặp lại tương tự cho các **Policies** tùy chỉnh nếu cần.

### 7. Xóa VPC và các Thành phần Mạng

1. Truy cập [VPC Console](https://console.aws.amazon.com/vpc).
2. Trong phần **Your VPCs**:
   - Chọn VPC đã tạo (ví dụ, **LabVPC**).
   - Click **Actions > Delete VPC** và xác nhận.
3. Đối với mỗi **Subnet** đã tạo:
   - Truy cập **Subnets** trong menu bên trái.
   - Chọn từng subnet liên quan đến **LabVPC** và click **Delete**.
4. Truy cập **Route Tables**:
   - Xóa các bảng định tuyến liên quan đến **LabVPC**.
5. Truy cập **Internet Gateways**:
   - Hủy liên kết gateway với **LabVPC** nếu có.
   - Chọn gateway và click **Delete Internet Gateway**.

### 8. Dừng và Xóa EC2 Instances

1. Truy cập [EC2 Console](https://console.aws.amazon.com/ec2).
2. Trong phần **Instances**:
   - Chọn các instance **Public** và **Private** đã tạo cho workshop.
   - Click **Actions > Instance State > Terminate**.
   - Xác nhận dừng và xóa.

---