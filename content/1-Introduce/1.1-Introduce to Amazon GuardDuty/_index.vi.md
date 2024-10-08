---
title : "Giới thiệu về Amazon GuardDuty"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 1.1 </b> "
---
### Giới thiệu về Amazon GuardDuty

**Amazon GuardDuty** là dịch vụ phát hiện mối đe dọa, liên tục giám sát môi trường AWS của bạn để phát hiện các hoạt động đáng ngờ hoặc độc hại. Nó sử dụng machine learning, giám sát phát hiện các mối đe dọa,tích hợp để phát hiện và cảnh báo cho bạn về các lỗ hổng tiềm tàng trong môi trường AWS như Amazon S3, EC2 Instances.

#### Trường hợp sử dụng:
1. Bảo vệ S3 Buckets: Phát hiện các dữ liệu,các tệp tin đáng ngờ hoặc lưu trữ phần mềm độc hại trong S3 Bucket.
2. Bảo vệ EC2 Instances: Xác định các instances được sử dụng để khai thác tiền điện tử hoặc kết nối với các địa chỉ IP đáng ngờ.
3. Giám sát hoạt động IAM Role: Phát hiện các hành vi bất thường trong truy cập role, chẳng hạn như cố gắng truy cập quyền hoặc vào các tài nguyên nhạy cảm.

![Sơ đồ kiến trúc](/images/gd.jpg?width=60pc)
