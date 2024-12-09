---
title : "Tạo Private Subnet"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.1.3 </b> "
---

#### Tạo Private Subnet

1. Nhấn chọn **Subnets**.
   - Nhấn chọn **Create subnet**.

![VPC](/images/2.prerequisite/017-createsubnet.png)

2. Tại trang **Create subnet**.
   - Tại mục **VPC ID**, chọn **Lab VPC**.
   - Trong mục **Subnet name**, điền **Lab Private Subnet**.
   - Tại mục **Availability Zone**, chọn Availability Zone đầu tiên.
   - Trong mục **IPv4 CIDR block**, điền **10.10.2.0/24**.

![VPC](/images/2.prerequisite/018-createsubnet.png)

3. Cuộn xuống cuối trang và nhấn chọn **Create subnet**.

Bước tiếp theo là tạo các security groups cần thiết cho bài lab.
