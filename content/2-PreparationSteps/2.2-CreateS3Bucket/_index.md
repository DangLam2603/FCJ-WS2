---
title : "Create S3 Bucket"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

### Create S3 Bucket
1. Access the AWS interface, find the **S3 service** and then click to select
2. In the S3 interface, click **Create bucket**
3. In the Create bucket interface:
   - AWS Region select **Singapore ap-southeast-1**
   - Bucket name enter **`s3-raw-gd`** 
![S3](/images/2.Bucket/2.1-bucket-raw.jpg?width=60pc)
4. Scroll down to the bottom and select **Create bucket**
![S3](/images/2.Bucket/2.3-create-bucket.jpg?width=60pc)
{{% notice warning %}}
You need to create another bucket to filter malicious files for later use. Follow and practice steps 1-4 from above, but change the bucket name to **s3-malware-gd**
{{% /notice %}}
1. Complete creating S3 bucket
![S3](/images/2.Bucket/2.4-2-bucket.jpg?width=60pc)

> For further practices, you can get the Bucket ARN by select the bucket name --> propertise --> copy the ARN
>
![S3](/images/2.Bucket/2.6-properties.jpg?width=60pc)
