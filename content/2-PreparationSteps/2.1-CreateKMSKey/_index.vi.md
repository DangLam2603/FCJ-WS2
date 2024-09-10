---
title : "Tạo khóa KMS"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

### Tạo khóa mã hóa KMS

1. Truy cập vào tài khoản AWS của bạn và tìm kiếm KMS (Key Management Service).
2. Nhấp chuột phải vào **Create Key** (Tạo Khóa)
![Git Bash](/images/1.Introduction/KMS/1.1.1-create%20KMS.jpg?width=60pc)
3. Trong phần cấu hình, chọn **Symmetric** và **Encrypt and Decrypt** (Mã hóa và Giải mã)
![Git Bash](/images/1.Introduction/KMS/1.1.2-config.jpg?width=60pc)
6. Trong phần Tùy chọn nâng cao (Advance options), chọn **KMS key** và **Single-Region Key** vì chúng ta muốn sử dụng khóa này trong cùng một khu vực trong buổi workshop.
![Git Bash](/images/1.Introduction/KMS/1.1.3.jpg?width=60pc)
5. Đặt **Alias custom name** (Tên bí danh tùy chỉnh) cho khóa KMS:
![Git Bash](/images/1.Introduction/KMS/1.1.4.jpg?width=60pc)
6. Chỉ định quyền truy cập quản trị viên (**permission**) cho khóa KMS:
![Git Bash](/images/1.Introduction/KMS/1.1.5.jpg?width=60pc) 
7. Xác định **mục đích sử dụng** của khóa KMS:
![Git Bash](/images/1.Introduction/KMS/1.1.6.jpg?width=60pc) 
8. Xem lại Chính sách Khóa (Key Policy)
![Git Bash](/images/1.Introduction/KMS/1.1.7-created.jpg?width=60pc) 
9. Khóa KMS đã được tạo thành công
![Git Bash](/images/1.Introduction/KMS/1.1.8.jpg?width=60pc) 

{{% notice note %}}
Trong bước Chính sách Khóa (Key Policy), bạn có thể giữ lại cấu hình mặc định được cung cấp khi tạo khóa KMS. Chúng ta sẽ thực hiện các sửa đổi cần thiết cho phần này sau khi tiếp tục dự án.
{{% /notice %}}
