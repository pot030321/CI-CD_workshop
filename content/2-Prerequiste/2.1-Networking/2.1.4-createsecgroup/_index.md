---
title : "Create Security Groups"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.1.4 </b> "
---

#### Create Security Groups

In this step, we will proceed to create the security groups used for our instances. As you can see, these security groups will not need to open traditional ports to **SSH** like port **22** or **remote desktop** through port **3389**.

#### Create Security Group for Linux Instance Located in Public Subnet

1. Go to [VPC service management console](https://console.aws.amazon.com/vpc).
   - Click **Security Group**.
   - Click **Create security group**.

![SG](/images/2.prerequisite/019-createsg.png)

2. In the **Security group name** field, enter **SG Public Linux Instance**.
   - In the **Description** section, enter **SG Public Linux Instance**.
   - In the **VPC** section, click the **X** to reselect the **Lab VPC** created for this lab.

![SG](/images/2.prerequisite/020-createsg.png)

3. Keep **Outbound rule** settings, scroll to the bottom, and click **Create security group**.

{{%notice tip%}}
As you can see, the security group created for the Linux public instance will not need to open traditional ports to **SSH** like port **22**.
{{%/notice%}}

#### Create a Security Group for a Windows Instance Located in a Private Subnet

1. After creating the security group for the Linux instance, click the Security Groups link to return to the list.
   - Click **Create security group**.

![SG](/images/2.prerequisite/021-createsg.png)

2. In the **Security group name** field, enter **SG Private Windows Instance**.
   - In the **Description** section, enter **SG Private Windows Instance**.
   - In the **VPC** section, click the **X** to reselect **Lab VPC**.

![SG](/images/2.prerequisite/022-createsg.png)

3. Scroll down.
   - Add **Outbound rule** to allow TCP 443 connection to **10.10.0.0/16** (CIDR of **Lab VPC**).
   - Click **Create security group**.

![SG](/images/2.prerequisite/023-createsg.png)

{{%notice tip%}}
For the instance in the private subnet, we will connect to the **Session Manager** endpoint over a TLS-encrypted connection, so we need to allow outbound connection to VPC CIDR through port 443.
{{%/notice%}}

#### Create Security Group for VPC Endpoint

1. In this step, we will create a security group for the VPC Endpoint of **Session Manager**.
2. After creating the security group for the Windows instance, click the Security Groups link.
   - Click **Create security group**.

3. In the **Security group name** field, enter **SG VPC Endpoint**.
   - In the **Description** section, enter **SG VPC Endpoint**.
   - In the **VPC** section, click the **X** to reselect **Lab VPC**.

![SG](/images/2.prerequisite/024-createsg.png)

4. Scroll down and delete the **Outbound rule**.

![SG](/images/2.prerequisite/025-createsg.png)

5. Add **Inbound rule** allowing TCP 443 from **10.10.0.0/16** (CIDR of **Lab VPC**).
   - Click **Create security group**.

![SG](/images/2.prerequisite/026-createsg.png)

With this, we have completed creating the necessary security groups for EC2 instances and VPC Endpoints.
