---
title : "Gán Policy cho S3"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 5.2 </b> "
---

#### Chỉnh sửa quyền bucket S3
1. Quay lại **Findings export options**, và nhấp vào **Configure now** trong phần bucket S3.

2. Trong giao diện **Export Findings**:
    - **S3 Bucket ARN** điền **ARN** của bucket mà bạn muốn xuất: **`s3-malware-gd`**.
    - **KMS Key ARN** điền **ARN** của khóa KMS mà chúng ta đã tạo trong **Bước chuẩn bị**

![S3](/images/5.%20Export%20Findings/5.4.jpg?width=60pc)
3. Tiếp theo, nhấp vào **View Policy for S3 Bucket** trong **Attach Policy**
![S3](/images/5.%20Export%20Findings/5.5.jpg?width=60pc)
4. Sao chép **JSON policy** và chuyển sang phần tiếp theo.
![S3](/images/5.%20Export%20Findings/5.6.jpg?width=60pc)
5. **Mở một tab mới** và điều hướng đến **Permission** của bucket **`s3-malware-gd`**
![S3](/images/5.%20Export%20Findings/5.7.jpg?width=60pc)
6. Trong **Bucket Policy**, nhấp vào **Edit**
![S3](/images/5.%20Export%20Findings/5.8.jpg?width=60pc)
7. Dán **JSON policy**. Nhấp vào **Save Change**
![S3](/images/5.%20Export%20Findings/5.8.jpg?width=60pc)
8. Hoàn tất việc Gán Policy cho S3
![S3](/images/5.%20Export%20Findings/5.9.jpg?width=60pc)
