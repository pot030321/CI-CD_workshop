---
title : "Tạo Security Groups"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.1.4 </b> "
---

#### Tạo Security Groups

Trong bước này, chúng ta sẽ tạo các security groups được sử dụng cho các instances. Những security groups này sẽ không cần mở các cổng truyền thống cho **SSH** như cổng **22** hoặc **remote desktop** qua cổng **3389**.

#### Tạo Security Group cho Linux Instance trong Public Subnet

1. Truy cập [giao diện quản trị dịch vụ VPC](https://console.aws.amazon.com/vpc).
   - Nhấn chọn **Security Group**.
   - Nhấn **Create security group**.

![SG](/images/2.prerequisite/019-createsg.png)

2. Tại mục **Security group name**, điền **SG Public Linux Instance**.
   - Trong phần **Description**, điền **SG Public Linux Instance**.
   - Trong mục **VPC**, nhấn **X** để chọn lại **Lab VPC** đã tạo cho bài lab.

![SG](/images/2.prerequisite/020-createsg.png)

3. Giữ nguyên thiết lập **Outbound rule**, cuộn xuống và nhấn **Create security group**.

{{%notice tip%}}
Như bạn thấy, security group này không cần mở các cổng truyền thống cho **SSH** như cổng **22**.
{{%/notice%}}

#### Tạo Security Group cho Windows Instance trong Private Subnet

1. Sau khi tạo security group cho Linux instance, nhấn vào liên kết **Security Groups** để quay lại danh sách.
   - Nhấn **Create security group**.

![SG](/images/2.prerequisite/021-createsg.png)

2. Tại mục **Security group name**, điền **SG Private Windows Instance**.
   - Trong phần **Description**, điền **SG Private Windows Instance**.
   - Trong mục **VPC**, nhấn **X** để chọn lại **Lab VPC**.

![SG](/images/2.prerequisite/022-createsg.png)

3. Cuộn xuống.
   - Thêm **Outbound rule** để cho phép kết nối TCP 443 tới **10.10.0.0/16** (CIDR của **Lab VPC**).
   - Nhấn **Create security group**.

![SG](/images/2.prerequisite/023-createsg.png)

{{%notice tip%}}
Với instance trong private subnet, chúng ta sẽ kết nối tới endpoint của **Session Manager** qua kết nối được mã hóa TLS, do đó cần cho phép kết nối outbound từ instance tới VPC CIDR qua cổng 443.
{{%/notice%}}

#### Tạo Security Group cho VPC Endpoint

1. Trong bước này, chúng ta sẽ tạo security group cho VPC Endpoint của **Session Manager**.
2. Sau khi tạo security group cho Windows instance, nhấn vào liên kết **Security Groups**.
   - Nhấn **Create security group**.

3. Tại mục **Security group name**, điền **SG VPC Endpoint**.
   - Trong phần **Description**, điền **SG VPC Endpoint**.
   - Trong mục **VPC**, nhấn **X** để chọn lại **Lab VPC**.

![SG](/images/2.prerequisite/024-createsg.png)

4. Cuộn xuống và xóa **Outbound rule**.

![SG](/images/2.prerequisite/025-createsg.png)

5. Thêm **Inbound rule** cho phép TCP 443 từ **10.10.0.0/16** (CIDR của **Lab VPC**).
   - Nhấn **Create security group**.

![SG](/images/2.prerequisite/026-createsg.png)

Với các bước này, chúng ta đã hoàn thành việc tạo các security groups cần thiết cho EC2 instances và VPC Endpoints.
