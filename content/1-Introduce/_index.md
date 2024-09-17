---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

### Introduction to architecture

In this workshop, we will explore the capabilities of **AWS GuardDuty** in securing your S3 bucket by integrating it with SNS and triggering events in EventBridge to alert the Admin for immediate action.

![GuardDuty example](/images/GD.png?featherlight=false&width=60pc)

### Architecture workflow
1. Enable Guard Duty for S3 malware protection
2. Set-up SNS, EventBridge rules for notification via email.
3. Set-up IAM roles, KMS for security.
4. Export Findings to S3 Bucket.


### Advantages of architecture
1. **Security**: this architecture helps us alarm action imediately if there are un-protected files in the S3 Bucket also AWS environment in general.
2. **Real-time Threat Detection**: AWS GuardDuty continuously monitors your S3 bucket for malicious or unauthorized access, helping detect threats in real-time without manual intervention.
3. **Automated Event Triggering**: When GuardDuty detects a suspicious event, it triggers an event in Amazon EventBridge, which allows for the automatic handling of these findings. In this workshop, we will send custom email via SNS.

### Related Sources 
1. [Creating custom responses to GuardDuty findings with Amazon CloudWatch Events](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_findings_cloudwatch.html)
2. [Exporting findings](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_exportfindings.html#guardduty_exportfindings-permissions)
3. [GuardDuty Malware Protection for S3](https://docs.aws.amazon.com/guardduty/latest/ug/gdu-malware-protection-s3.html)
