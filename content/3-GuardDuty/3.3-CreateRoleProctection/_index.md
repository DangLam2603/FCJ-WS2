---
title : "Create IAM Protection Role "
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

### Overview
In this following step, we have create an IAM role base on the prervious policy for further use to specify Permission in GuardDuty

1. In the **IAM** interface, select **Role** from the left navigation bar and **Create Role**
![IAM Role](/images/3.GuardDuty/3.17-role.jpg?width=60pc)
1. In the **Select trusted entity**, select **Custom Trust Policy**
![IAM Role](/images/3.GuardDuty/3.18.jpg?width=60pc)
1. Select the following policy ```pl-gd-s3-raw``` 
![IAM Role](/images/3.GuardDuty/3.19.jpg?width=60pc)
1. Next, select **Role name** in the **Role details** section.
- In the **Trust Policy**, paste the previous **Trust Relationship** in **3.1 section**
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "malware-protection-plan.guardduty.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
![IAM Role](/images/3.GuardDuty/3.20.jpg?width=60pc)
5. Review the Role and Create new Role: 
![IAM Role](/images/3.GuardDuty/3.21.jpg?width=60pc)
6. Complete create role
 ![IAM Role](/images/3.GuardDuty/3.22.jpg?width=60pc)