---
title : "Dòng Công Việc Demo"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

#### Tổng Quan
Bây giờ bạn đã cấu hình xong mọi thứ, hãy cùng đi qua các bản demo và xem cách nó hoạt động thực tế.

#### Tải các tệp nghi ngờ lên S3
{{% notice warning %}}
Chỉ dành cho mục đích demo! Bạn nên tránh tải lên các tệp nghi ngờ vào bucket S3 của bạn, vì điều này có thể dẫn đến việc dịch vụ bị ngừng hoạt động hoặc tồi tệ hơn. Trong hướng dẫn này, tôi sẽ sử dụng một tệp thử nghiệm Malware. Bạn có thể theo dõi và tải xuống từ [liên kết này](https://www.eicar.org/download-anti-malware-testfile/#top).
{{% /notice %}}

1. Điều hướng đến ```s3-raw-gd``` và nhấp vào **Tải lên** 
![](/images/6.Demo/1.jpg?width=60pc)
2. Tải tệp malware ```virusFile.txt``` lên bucket S3 được cấu hình bảo vệ ```s3-raw-gd```
![](/images/6.Demo/2.jpg?width=60pc)
3. Ngay lập tức, GuardDuty sẽ quét tất cả các tệp trong bucket và gán nhãn **Trạng Thái Quét**
   - Các giá trị trạng thái kết quả quét tiềm năng của đối tượng S3
     + NO_THREATS_FOUND – GuardDuty không phát hiện mối đe dọa tiềm năng liên quan đến đối tượng đã quét.
     + THREATS_FOUND – GuardDuty phát hiện mối đe dọa tiềm năng liên quan đến đối tượng đã quét.
     + UNSUPPORTED – Có một số lý do mà Malware Protection for S3 sẽ bỏ qua quét. Các lý do tiềm năng bao gồm tệp được bảo vệ bằng mật khẩu, hạn ngạch của Malware Protection for S3 và hỗ trợ cho một số tính năng Amazon S3 có thể không khả dụng. Để biết thêm thông tin, hãy xem Các khả năng của Malware Protection for S3.
     + ACCESS_DENIED – GuardDuty không thể truy cập đối tượng này để quét. Kiểm tra quyền IAM liên quan đến bucket này. Để biết thêm thông tin, hãy xem Điều kiện tiên quyết - Tạo hoặc cập nhật chính sách IAM.
     + FAILED – GuardDuty không thể thực hiện quét malware trên đối tượng này do lỗi nội bộ.
![](/images/6.Demo/3.jpg?width=60pc)
4. Trong Console GuardDuty, bạn có thể tìm thấy tất cả các kết quả mà GuardDuty phát hiện ở đây.
![](/images/6.Demo/4.jpg?width=60pc)

#### Thông Báo
1. Sau khi phát hiện kết quả, bạn sẽ nhận được email mà bạn đã cấu hình trước đó.
![](/images/6.Demo/5.jpg?width=60pc)

#### Xuất S3 Bucket 
1. Điều hướng đến bucket ```s3-malware-gd```
![](/images/6.Demo/6.jpg?width=60pc)
2. Bạn có thể tìm thấy các kết quả trong bucket đã được mã hóa ở đây
![](/images/6.Demo/7.jpg?width=60pc)
