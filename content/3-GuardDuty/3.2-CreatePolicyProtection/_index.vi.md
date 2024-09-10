---
title : "Tạo Chính Sách Bảo Vệ IAM"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

### Tổng Quan
Trong bước trước, chúng ta đã tạo và chỉnh sửa bảo vệ phần mềm độc hại và nhận được một chính sách JSON. Bây giờ, hãy tùy chỉnh Chính sách IAM để làm cho điều này hoạt động!

1. Trong giao diện AWS Console, tìm kiếm và chọn **IAM** 
![IAM Role](/images/3.GuardDuty/3.10-IAM.jpg?width=60pc)
2. Trong thanh điều hướng bên trái, chọn **Policies** và chọn **Create Policy**
![IAM Role](/images/3.GuardDuty/3.11.jpg?width=60pc)
3. Trong phần Quyền cụ thể:
   - Chọn **JSON options** 
   - Dán chính sách **Policy** trước đó vào **phần 3.1**
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowManagedRuleToSendS3EventsToGuardDuty",
      "Effect": "Allow",
      "Action": [
        "events:PutRule",
        "events:DeleteRule",
        "events:PutTargets",
        "events:RemoveTargets"
      ],
      "Resource": [
        "arn:aws:events:ap-southeast-1:381492162967:rule/DO-NOT-DELETE-AmazonGuardDutyMalwareProtectionS3*"
      ],
      "Condition": {
        "StringLike": {
          "events:ManagedBy": "malware-protection-plan.guardduty.amazonaws.com"
        }
      }
    },
    {
      "Sid": "AllowGuardDutyToMonitorEventBridgeManagedRule",
      "Effect": "Allow",
      "Action": [
        "events:DescribeRule",
        "events:ListTargetsByRule"
      ],
      "Resource": [
        "arn:aws:events:ap-southeast-1:381492162967:rule/DO-NOT-DELETE-AmazonGuardDutyMalwareProtectionS3*"
      ]
    },
    {
      "Sid": "AllowPostScanTag",
      "Effect": "Allow",
      "Action": [
        "s3:PutObjectTagging",
        "s3:GetObjectTagging",
        "s3:PutObjectVersionTagging",
        "s3:GetObjectVersionTagging"
      ],
      "Resource": [
        "arn:aws:s3:::<bucket_name>/*"
      ]
    },
    {
      "Sid": "AllowEnableS3EventBridgeEvents",
      "Effect": "Allow",
      "Action": [
        "s3:PutBucketNotification",
        "s3:GetBucketNotification"
      ],
      "Resource": [
        "arn:aws:s3:::<bucket_name>"
      ]
    },
    {
      "Sid": "AllowPutValidationObject",
      "Effect": "Allow",
      "Action": [
        "s3:PutObject"
      ],
      "Resource": [
        "arn:aws:s3:::<bucket_name>/malware-protection-resource-validation-object"
      ]
    },
    {
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket"
      ],
      "Resource": [
        "arn:aws:s3:::<bucket_name>"
      ]
    },
    {
      "Sid": "AllowMalwareScan",
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:GetObjectVersion"
      ],
      "Resource": [
        "arn:aws:s3:::<bucket_name>/*"
      ]
    },
    {
      "Sid": "AllowDecryptForMalwareScan",
      "Effect": "Allow",
      "Action": [
        "kms:GenerateDataKey",
        "kms:Decrypt"
      ],
      "Resource": "arn:aws:kms:ap-southeast-1:381492162967:key/<key_id>",
      "Condition": {
        "StringLike": {
          "kms:ViaService": "s3.*.amazonaws.com"
        }
      }
    }
  ]
}
```
![IAM Role](/images/3.GuardDuty/3.12.jpg?width=60pc)
4. Tiếp theo đến bước Xem xét và Tạo, chọn tên chính sách trong **Policy Details**, chúng ta sẽ chọn ```pl-gd-s3-raw``` 
![IAM Role](/images/3.GuardDuty/3.13.jpg?width=60pc)
5. Xem xét Chính sách:
   - **EventBridge**: Quyền truy cập hạn chế với các quyền Danh sách, Đọc và Ghi. Nó có các điều kiện để quản lý các sự kiện từ Amazon GuardDuty liên quan đến bảo vệ phần mềm độc hại.
   - **KMS (Key Management Service)**: Quyền ghi được cấp với các hạn chế dựa trên ID khóa và khu vực, và phải được truy cập qua dịch vụ S3.
   - **S3 (Simple Storage Service)**: Quyền Danh sách, Đọc, Ghi và Đánh dấu, không có điều kiện cụ thể nào được áp dụng.
![IAM Role](/images/3.GuardDuty/3.14.jpg?width=60pc)
6. Tạo Chính sách
 ![IAM Role](/images/3.GuardDuty/3.15.jpg?width=60pc)
7. Hoàn thành việc tạo chính sách
 ![IAM Role](/images/3.GuardDuty/3.16.jpg?width=60pc)
