---
title : "Malware Protection cho S3 bằng GuardDuty"
date : "`r Sys.Date()`"
weight : 1
chapter : false
---

# Bảo Vệ Malware cho S3 với GuardDuty

#### Tổng Quan

Trong workshop này, chúng tôi sẽ trình bày cách AWS GuardDuty có thể bảo vệ bucket S3 của bạn bằng cách nhận diện và khắc phục các tệp độc hại. Bạn sẽ học cách phát hiện các mối đe dọa tự động, xuất các phát hiện GuardDuty được mã hóa vào bucket S3 và thiết lập cảnh báo thời gian thực trong các khoảng thời gian chính sử dụng EventBridge và SNS để thông báo cho các quản trị viên.

![Sơ đồ kiến trúc](/images/GD.png?width=60pc)

#### Nội Dung

1. [Giới thiệu](1-introduce/)
2. [Các bước chuẩn bị](2-preparationsteps/)
3. [Amazon GuardDuty](3-guardduty/)
4. [Thiết lập thông báo](4-setupnotification/)
5. [Xuất kết quả đến S3](5-exportfindingtos3/)
6. [Demo](6-demo/)
7. [Dọn dẹp tài nguyên](7-cleanupresources/)
