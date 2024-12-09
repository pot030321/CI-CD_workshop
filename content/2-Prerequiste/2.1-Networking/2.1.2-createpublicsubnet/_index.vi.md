---
title : "Tạo Public subnet"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.1.2 </b> "
---

#### Tạo Public subnet

1. Nhấn chọn **Subnets**.
   - Nhấn chọn **Create subnet**.

![VPC](/images/2.prerequisite/003-createsubnet.png)

2. Tại trang **Create subnet**.
   - Tại mục **VPC ID**, chọn **Lab VPC**.
   - Tại mục **Subnet name**, điền **Lab Public Subnet**.
   - Tại mục **Availability Zone**, chọn Availability Zone đầu tiên.
   - Tại mục **IPv4 CIDR block**, điền **10.10.1.0/24**.

![VPC](/images/2.prerequisite/004-createsubnet.png)

3. Cuộn xuống cuối trang và nhấn chọn **Create subnet**.

4. Chọn **Lab Public Subnet** vừa tạo.
   - Nhấn chọn **Actions**.
   - Nhấn chọn **Edit subnet settings**.

![VPC](/images/2.prerequisite/005-createsubnet.png)

5. Kích hoạt **Enable auto-assign public IPv4 address**.
   - Nhấn **Save**.

![VPC](/images/2.prerequisite/006-createsubnet.png)

6. Nhấn chọn **Internet Gateways**.
   - Nhấn chọn **Create internet gateway**.
  
![VPC](/images/2.prerequisite/007-createigw.png)

7. Tại trang **Create internet gateway**.
   - Tại mục **Name tag**, điền **Lab IGW**.
   - Nhấn **Create internet gateway**.
  
![VPC](/images/2.prerequisite/008-createigw.png)

8. Sau khi tạo thành công, chọn **Actions**.
   - Nhấn **Attach to VPC**.
 
![VPC](/images/2.prerequisite/009-createigw.png)

9. Tại trang **Attach to VPC**.
   - Tại mục **Available VPCs**, chọn **Lab VPC**.
   - Nhấn **Attach internet gateway**.
   - Kiểm tra quá trình gắn kết thành công như hình dưới.

![VPC](/images/2.prerequisite/010-createigw.png)

10. Tiếp theo, chúng ta sẽ tạo một custom route table để gán vào **Lab Public Subnet**.
   - Nhấn chọn **Route Tables**.
   - Nhấn chọn **Create route table**.

![VPC](/images/2.prerequisite/011-creatertb.png)

11. Tại trang **Create route table**.
   - Tại mục **Name**, điền **Lab Publicrtb**.
   - Tại mục **VPC**, chọn **Lab VPC**.
   - Nhấn **Create route table**.

12. Sau khi tạo route table thành công.
   - Nhấn **Edit routes**.
  
![VPC](/images/2.prerequisite/012-creatertb.png)

13. Tại trang **Edit routes**.
   - Nhấn **Add route**.
   - Tại mục **Destination**, điền **0.0.0.0/0**.
   - Tại mục **Target**, chọn **Internet Gateway**, sau đó chọn **Lab IGW**.
   - Nhấn **Save changes**.

![VPC](/images/2.prerequisite/013-creatertb.png)

14. Nhấn tab **Subnet associations**.
   - Nhấn **Edit subnet associations** để gán custom route table vừa tạo vào **Lab Public Subnet**.

![VPC](/images/2.prerequisite/014-creatertb.png)

15. Tại trang **Edit subnet associations**. 
   - Chọn **Lab Public Subnet**.
   - Nhấn **Save associations**.

![VPC](/images/2.prerequisite/015-creatertb.png)

16. Kiểm tra thông tin route table đã được gắn kết với **Lab Public Subnet** và thông tin route đi Internet đã được trỏ đến Internet Gateway như hình dưới.

![VPC](/images/2.prerequisite/016-creatertb.png)
