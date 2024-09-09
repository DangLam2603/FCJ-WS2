---
title : "Introduce to Amazon GuardDuty"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 1.1 </b> "
---
##  Explaination of Amazon GuardDuty


**Amazon GuardDuty** is a threat detection service that continuously monitors your AWS environment for suspicious or malicious activity. It uses machine learning, monitoring detection, and integrated threat intelligence to detect and alert you about potential threats in AWS enviroment like Amazon S3, EC2 Instances.

**Use Cases:**
1. Protecting S3 Buckets: Detecting suspicious data, files or the storage of malware in S3.
2. Protecting EC2 Instances: Identifying instances used for crypto mining or connecting to suspicious IP addresses.
3. Monitoring IAM Role Activity: Spotting anomalies in role access, like attempts to escalate privileges or access sensitive resources.

![Architecture diagram](/images/gd.jpg?width=60pc)