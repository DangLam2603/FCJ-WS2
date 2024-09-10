---
title : "Tạo Vai Trò Bảo Vệ IAM"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

### Tổng Quan
Trong bước tiếp theo, chúng ta sẽ tạo một vai trò IAM dựa trên chính sách trước đó để sử dụng thêm nhằm chỉ định Quyền trong GuardDuty.

1. Trong giao diện **IAM**, chọn **Role** từ thanh điều hướng bên trái và **Create Role**
![IAM Role](/images/3.GuardDuty/3.17-role.jpg?width=60pc)
2. Trong **Select trusted entity**, chọn **Custom Trust Policy**
![IAM Role](/images/3.GuardDuty/3.18.jpg?width=60pc)
3. Chọn chính sách sau ```pl-gd-s3-raw``` 
![IAM Role](/images/3.GuardDuty/3.19.jpg?width=60pc)
4. Tiếp theo, chọn **Role name** trong phần **Role details**.
- Trong **Trust Policy**, dán **Trust Relationship** trước đó vào **phần 3.1**
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "malware-protection-plan.guardduty.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
![IAM Role](/images/3.GuardDuty/3.20.jpg?width=60pc)
5. Xem xét Vai trò và Tạo Vai trò mới: 
![IAM Role](/images/3.GuardDuty/3.21.jpg?width=60pc)
6. Hoàn thành việc tạo vai trò
 ![IAM Role](/images/3.GuardDuty/3.22.jpg?width=60pc)
