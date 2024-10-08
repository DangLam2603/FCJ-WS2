---
title : "Tạo SNS"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

### Tạo SNS để gửi email
Trong phần này, chúng ta sẽ cấu hình dịch vụ Email sử dụng chủ đề SNS.

### Tạo Chủ Đề
1. Điều hướng đến **AWS console**, tìm kiếm dịch vụ **SNS**.
![SNS](/images/4.Notification/SNS/4.1.1-sns.jpg?width=60pc)

2. Chọn **Create Topic**.
![SNS](/images/4.Notification/SNS/4.1.2-topic.jpg?width=60pc)

3. Trong phần Chi tiết, chọn loại **Standard** và dán ```guardduty-topic``` vào phần **Name**.
![SNS](/images/4.Notification/SNS/4.1.3.jpg?width=60pc)

4. Sau đó, nhấp **Create Topic**
![SNS](/images/4.Notification/SNS/4.1.4.jpg?width=60pc)

### Tạo và Đăng Ký Subscription

1. Điều hướng đến thanh bên trái và chọn **Topic**:
   - Chọn chủ đề mà chúng ta vừa tạo
   - sau đó chọn **subscription** và nhấp **create subscription**  
![SNS](/images/4.Notification/SNS/4.1.5-subscription.jpg?width=60pc)
1. Trong phần Chi tiết, chọn **Email** ở phần **Protocol**
![SNS](/images/4.Notification/SNS/4.1.6.jpg?width=60pc)
1. Tiếp theo, chỉ định **email** sẽ nhận thông báo từ SNS 
![SNS](/images/4.Notification/SNS/4.1.7.jpg?width=60pc)
1. Nhấp **Tạo Đăng ký**
![SNS](/images/4.Notification/SNS/4.1.8.jpg?width=60pc)
1. Hoàn thành việc tạo đăng ký.
![SNS](/images/4.Notification/SNS/4.1.9.jpg?width=60pc)
{{% notice info %}}
Sau khi bạn tạo đăng ký, trạng thái tiếp theo sẽ chờ xác nhận. Bạn sẽ nhận được một email xác nhận dựa trên email mà bạn cung cấp ở trên.
{{% /notice %}} 
![SNS](/images/4.Notification/SNS/4.1.10.jpg?width=60pc)
### Xác Nhận Email
1. Email đã được xác nhận thành công.
![SNS](/images/4.Notification/SNS/4.1.11.jpg?width=60pc)
1. Cập nhật trạng thái
![SNS](/images/4.Notification/SNS/4.1.12.jpg?width=60pc)
