---
title : "Attach Policy to S3"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 5.2 </b> "
---

#### Modify S3 bucket permission
1. Navigate back to **Findings export options**, and click on **Configure now** in the S3 bucket section

2. In the **Export Findings** interface:
    - **S3 Bucket ARN** fill in the **ARN** of the bucket that you want to export: **`s3-malware-gd`**.
    - **KMS Key ARN** fill in the **ARN** path of that KMS key we created in **Preparaton Step**

![S3](/images/5.%20Export%20Findings/5.4.jpg?width=60pc)
1. Next, Click on **View Policy for S3 Bucket** in the **Attach Policy**
![S3](/images/5.%20Export%20Findings/5.5.jpg?width=60pc)
1. Copy a **JSON policy** and move to next part.
![S3](/images/5.%20Export%20Findings/5.6.jpg?width=60pc)
1. **Open a new tab** and navigate to the **`s3-malware-gd`** bucket **Permission**
![S3](/images/5.%20Export%20Findings/5.7.jpg?width=60pc)
1. In the **Bucket Policy**, click **Edit**
![S3](/images/5.%20Export%20Findings/5.8.jpg?width=60pc)
1. Paste the **JSON policy**. Click **Save Change**
![S3](/images/5.%20Export%20Findings/5.8.jpg?width=60pc)
1. Completely Attach Policy to S3
![S3](/images/5.%20Export%20Findings/5.9.jpg?width=60pc)