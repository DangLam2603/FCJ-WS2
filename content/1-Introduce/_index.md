---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

## Introduction to architecture

In this workshop, we will explore the capabilities of **AWS GuardDuty** in securing your S3 bucket by integrating it with SNS and triggering events in EventBridge to alert the Admin for immediate action.

![GuardDuty example](/images/GD.png?featherlight=false&width=60pc)

**This architecture includes**
1. Enable Guard Duty for S3 malware protection.
2. Set-up SNS, EventBridge rules for notification via email.
3. Set-up IAM roles, KMS for security.
4. Export Findings to S3 Bucket.

**Advantages of implementing this architecture:**
1. **Security**: this architecture helps us alarm action imediately if there are un-protected files in the S3 Bucket also AWS environment in general.
2. **Real-time Threat Detection**: AWS GuardDuty continuously monitors your S3 bucket for malicious or unauthorized access, helping detect threats in real-time without manual intervention.
3. **Automated Event Triggering**: When GuardDuty detects a suspicious event, it triggers an event in Amazon EventBridge, which allows for the automatic handling of these findings. In this workshop, we will send custom email via SNS.