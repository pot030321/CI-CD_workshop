---
title: "Tạo Repository trên ECR"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 5.4.1 </b> "
---

#### Tạo Repository trên ECR

1. Truy cập vào [giao diện quản trị dịch vụ ECR](https://console.aws.amazon.com/ecr/home).
   - Nhấn **Create repository**.
   - Trong **Repository name**, nhập tên repository, ví dụ: `myapp-ecr-repo`.
   - Chọn các tùy chọn khác nếu cần, như scan on push để quét bảo mật khi đẩy image mới.

2. Nhấn **Create repository** để hoàn tất.

3. Ghi lại URI của repository để sử dụng trong quá trình build và deploy Docker image.
