---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

## Giới thiệu về kiến trúc

Trong buổi workshop này, chúng ta sẽ khám phá khả năng của **AWS GuardDuty** trong việc bảo vệ S3 bucket của bạn bằng cách tích hợp với SNS và kích hoạt các sự kiện trong EventBridge để cảnh báo cho Admin hành động kịp thời.

![GuardDuty example](/images/GD.png?featherlight=false&width=50pc)

**Kiến trúc này bao gồm**:
- Kích hoạt GuardDuty để bảo vệ S3 khỏi phần mềm độc hại.
- Thiết lập SNS, các quy tắc EventBridge để nhận thông báo qua email.
- Thiết lập IAM roles, KMS để bảo mật.
- Xuất kết quả tìm được vào S3 Bucket.

**Lợi ích của việc triển khai kiến trúc này:**
- **Bảo mật**: kiến trúc này giúp chúng ta cảnh báo ngay lập tức nếu có các tệp không được bảo vệ trong S3 Bucket cũng như môi trường AWS nói chung.
- **Phát hiện mối đe dọa theo thời gian thực**: AWS GuardDuty liên tục giám sát S3 bucket của bạn để phát hiện các truy cập độc hại hoặc không được phép, giúp phát hiện các mối đe dọa theo thời gian thực mà không cần can thiệp thủ công.
- **Kích hoạt sự kiện tự động**: Khi GuardDuty phát hiện một sự kiện đáng ngờ, nó sẽ kích hoạt sự kiện trong Amazon EventBridge, cho phép xử lý tự động các phát hiện này. Trong buổi workshop này, chúng ta sẽ gửi email tùy chỉnh qua SNS.
