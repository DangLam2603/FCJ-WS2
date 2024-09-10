---
title : "Cài Đặt Tần Suất"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 5.1 </b> "
---

#### Cài Đặt GuardDuty
Trong phần này, chúng ta sẽ cấu hình tần suất cho phép EventBridge xuất các phát hiện sau một khoảng thời gian.

1. Điều hướng đến thanh bên trái của GuardDuty, chọn **Cài đặt**
![Settings](/images/5.%20Export%20Findings/5.1-settings.jpg?width=60pc)
2. Sau đó, nhấp vào **Chỉnh sửa** trong phần **Tần suất** của **Tùy chọn Xuất Phát Hiện**
![Settings](/images/5.%20Export%20Findings/5.2.jpg?width=60pc)
3. Trong cửa sổ pop-up, bạn có thể chọn tần suất mà bạn muốn EventBridge xuất.
   - 6 Giờ (mặc định)
   - 1 Giờ
   - 15 Phút (Chúng tôi sẽ chọn 15 phút cho workshop này).
![Settings](/images/5.%20Export%20Findings/5.3.jpg?width=60pc)
