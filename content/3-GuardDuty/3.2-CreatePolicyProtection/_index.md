---
title : "Create IAM Protection Policy "
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

## Overview
In the previous step, we have create and modify the malware protection and recieve a JSON Policy. Now let custom IAM Policy to make this works!

1. In the AWS Console interface, search and select **IAM** 
![IAM Role](/images/3.GuardDuty/3.10-IAM.jpg?width=60pc)
2. In the left-side navigate bar, select **Policies** and choose **Create Policy**
![IAM Role](/images/3.GuardDuty/3.11.jpg?width=60pc)
3. In the Specific Permission section:
   - Select **JSON options** 
   - Paste the previous Permission **Policy** in **3.1 sections**
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
4. Next to Review and Create step,choose a policy name in the **Policy Details**, we will go for ```pl-gd-s3-raw``` 
![IAM Role](/images/3.GuardDuty/3.13.jpg?width=60pc)
5. Review the Policy:
   - **EventBridge**: Limited access with List, Read, and Write permissions. It has conditions to manage events from Amazon GuardDuty related to malware protection.
   - **KMS (Key Management Service)**: Write permissions are provided with restrictions based on key IDs and regions, and must be accessed through the S3 service.
   - **S3 (Simple Storage Service)**: List, Read, Write, and Tagging permissions, with no specific conditions applied.
![IAM Role](/images/3.GuardDuty/3.14.jpg?width=60pc)
6. Create Policy
 ![IAM Role](/images/3.GuardDuty/3.15.jpg?width=60pc)
7. Complete create policy
 ![IAM Role](/images/3.GuardDuty/3.16.jpg?width=60pc)