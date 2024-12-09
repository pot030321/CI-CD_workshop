---
title : "Tạo Private Instance"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

1. Truy cập [giao diện quản trị dịch vụ EC2](https://console.aws.amazon.com/ec2/v2/home).
   - Nhấn chọn **Instances**.
   - Nhấn **Launch instances**.
  
2. Tại trang **Step 1: Choose an Amazon Machine Image (AMI)**.
   - Cuộn xuống.
   - Nhấn **Select** để chọn AMI **Microsoft Windows Server 2019 Base**.
  
![EC2](/images/2.prerequisite/034-createec2.png)

3. Tại trang **Step 2: Choose an Instance Type**.
   - Chọn loại instance **t2.micro**.
   - Nhấn **Next: Configure Instance Details**.
 
![EC2](/images/2.prerequisite/029-createec2.png)

4. Tại trang **Step 3: Configure Instance Details**.
   - Tại mục **Network**, chọn **Lab VPC**.
   - Tại mục **Subnet**, chọn **Lab Private Subnet**.
   - Tại mục **Auto-assign Public IP**, chọn **Use subnet setting (Disable)**.
   - Nhấn **Next: Add Storage**.

![EC2](/images/2.prerequisite/035-createec2.png)

5. Nhấn **Next: Add Tags** để chuyển đến bước tiếp theo.
   - Nhấn **Next: Configure Security Group** để tiếp tục.

6. Tại trang **Step 6: Configure Security Group**.
   - Chọn **Select an existing security group**.
   - Chọn security group **SG Private Windows Instance**.
   - Nhấn **Review and Launch**.

![EC2](/images/2.prerequisite/036-createec2.png)

7. Hộp thoại cảnh báo xuất hiện do chưa cấu hình firewall cho phép kết nối tới cổng 22. Nhấn **Continue** để tiếp tục.

8. Tại trang **Step 7: Review Instance Launch**.
   - Nhấn **Launch**.

9. Trong hộp thoại **Select an existing key pair or create a new key pair**.
   - Chọn **Choose an existing key pair**.
   - Tại mục **Key pair name**, chọn **LabKeypair**.
   - Chọn hộp kiểm **I acknowledge that I have access to the corresponding private key file, and that without this file, I won't be able to log into my instance.**
   - Nhấn **Launch Instances** để tạo EC2 instance.

10. Nhấn **View Instances** để quay lại danh sách các EC2 instances.

11. Nhấn biểu tượng chỉnh sửa dưới cột **Name**.
   - Trong hộp thoại **Edit Name**, điền **Private Windows Instance**.
   - Nhấn **Save**.

![EC2](/images/2.prerequisite/033-createec2.png)

Tiếp theo, chúng ta sẽ tạo IAM Roles để hỗ trợ cho Session Manager.
