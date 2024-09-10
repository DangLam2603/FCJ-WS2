---
title : "Tạo S3 Bucket"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

## Tạo S3 Bucket
1. Truy cập giao diện AWS, tìm **Dịch vụ S3** và nhấp chọn
2. Trong giao diện S3, nhấp vào **Create bucket** (Tạo Bucket)
3. Trong giao diện Tạo Bucket:
   - AWS Region chọn **Singapore ap-southeast-1**
   - Tên Bucket nhập **`s3-raw-gd`**
![S3](/images/2.Bucket/2.1-bucket-raw.jpg?width=60pc)
4. Cuộn xuống dưới cùng và chọn **Create bucket** (Tạo Bucket)
![S3](/images/2.Bucket/2.3-create-bucket.jpg?width=60pc)
{{% notice warning %}}
Bạn cần tạo thêm một bucket khác để lọc các tập tin độc hại cho việc sử dụng sau này. Thực hiện và làm theo các bước 1-4 ở trên, nhưng thay đổi tên bucket thành **s3-malware-gd**
{{% /notice %}}
1. Hoàn thành việc tạo S3 Bucket
![S3](/images/2.Bucket/2.4-2-bucket.jpg?width=60pc)

> Để thực hành thêm, bạn có thể lấy ARN của Bucket bằng cách chọn tên bucket --> thuộc tính --> sao chép ARN
>
![S3](/images/2.Bucket/2.6-properties.jpg?width=60pc)
