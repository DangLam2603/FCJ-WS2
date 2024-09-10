---
title : "Tạo Sự Kiện cho GuardDuty"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

## Tổng Quan
Trong phần này, chúng ta sẽ triển khai kiến trúc dựa trên sự kiện để theo dõi các phát hiện từ Amazon GuardDuty theo thời gian thực. Sử dụng Amazon EventBridge, chúng ta sẽ tạo các quy tắc kích hoạt các hành động cụ thể khi GuardDuty phát hiện các mối đe dọa hoặc lỗ hổng tiềm ẩn.

1. Trong thanh tìm kiếm AWS, gõ **EventBridge** và chọn kết quả đầu tiên.
![EventBridge](/images/4.Notification/EventBridge/4.2.1-started.jpg?width=60pc)

1. Chuyển đến tab **EventBridge Rule** và nhấp **Create Rule**
![EventBridge](/images/4.Notification/EventBridge/4.2.2.jpg?width=60pc)

1. Gõ ```rule-event-gd``` vào phần Tên, và để các tùy chọn còn lại ở mặc định
![EventBridge](/images/4.Notification/EventBridge/4.2.3.jpg?width=60pc)

1. Trong **Event Pattern**, chọn các tùy chọn sau:
   - **Event Source**, Chọn **AWS service**
   - Chọn **GuardDuty** cho **AWS service**
   - **GuardDuty Findings** cho **Event Type**.

Sau đó, chọn **Edit Pattern** để thay đổi mức độ nghiêm trọng của sự kiện sẽ được kích hoạt.
![EventBridge](/images/4.Notification/EventBridge/4.2.5.jpg?width=60pc)

5. Dán đoạn mã sau và chỉnh sửa mức độ nguy hiểm của các phát hiện
```
{ "source": [ "aws.guardduty" ], "detail-type": [ "GuardDuty Finding" ], "detail": { "severity": [ 4, 4.0, 4.1, 4.2, 4.3, 4.4, 4.5, 4.6, 4.7, 4.8, 4.9, 5, 5.0, 5.1, 5.2, 5.3, 5.4, 5.5, 5.6, 5.7, 5.8, 5.9, 6, 6.0, 6.1, 6.2, 6.3, 6.4, 6.5, 6.6, 6.7, 6.8, 6.9, 7, 7.0, 7.1, 7.2, 7.3, 7.4, 7.5, 7.6, 7.7, 7.8, 7.9, 8, 8.0, 8.1, 8.2, 8.3, 8.4, 8.5, 8.6, 8.7, 8.8, 8.9 ] } }
```
![EventBridge](/images/4.Notification/EventBridge/4.2.6.jpg?width=60pc)
6. Trong Cài đặt Nâng cao, chọn các tùy chọn sau:
   - Chọn dịch vụ AWS
   - Chọn **SNS topic**
   - Và trong phần **Topic**, chọn ```guardduty-topic```, mà bạn vừa tạo
![EventBridge](/images/4.Notification/EventBridge/4.2.7.jpg?width=60pc)  
7. Tiếp theo, chúng ta sẽ tạo thông báo tùy chỉnh cho SNS:
   - Trong **Additional settings**, chọn **Input transformer**
![EventBridge](/images/4.Notification/EventBridge/4.2.8.jpg?width=60pc)
8. Trong **Target input transformer**, gõ đoạn mã sau vào **Input Path**:
```
{
    "severity": "$.detail.severity",
    "Account_ID": "$.detail.accountId",
    "Finding_ID": "$.detail.id",
    "Finding_Type": "$.detail.type",
    "region": "$.region",
    "Finding_description": "$.detail.description"
}
                            
```
![EventBridge](/images/4.Notification/EventBridge/4.2.9.jpg?width=60pc)
9. Trong **Template**, cung cấp **Input Template** sau:
```
"AWS <Account_ID> has a severity <severity> GuardDuty finding type <Finding_Type> in the <region> region."
"Finding Description:"
"<Finding_description>. "
"For more details open the GuardDuty console at https://console.aws.amazon.com/guardduty/home?region=<region>#/findings?search=id%3D<Finding_ID>"                         
```
![EventBridge](/images/4.Notification/EventBridge/4.2.10.jpg?width=60pc)
1.  Xem lại và nhấp Create Rule
![EventBridge](/images/4.Notification/EventBridge/4.2.12.jpg?width=60pc)
1.  Hoàn tất việc tạo Event Rule
![EventBridge](/images/4.Notification/EventBridge/4.2.13.jpg?width=60pc)

