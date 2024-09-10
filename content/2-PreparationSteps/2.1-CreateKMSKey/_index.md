---
title : "Create KMS key"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

## Create KMS encrypted keys

1. Access your AWS account and Search for KMS (Key Management Service).
2. Right-click to **Create Key**
![Git Bash](/images/1.Introduction/KMS/1.1.1-create%20KMS.jpg?width=60pc)
3. For the configurtion, select **Symmetric** and **Encrypt and Decrypt**
![Git Bash](/images/1.Introduction/KMS/1.1.2-config.jpg?width=60pc)
6. In the Advance options, select **KMS key** and **Single-Region Key** while we want to use this key in the same region in the workshop.
![Git Bash](/images/1.Introduction/KMS/1.1.3.jpg?width=60pc)
5. Give the KMS key an **Alias custom name**:
![Git Bash](/images/1.Introduction/KMS/1.1.4.jpg?width=60pc)
6. Specify the admin **permission** for KMS access:
![Git Bash](/images/1.Introduction/KMS/1.1.5.jpg?width=60pc) 
7. Define the **usage** of the KMS Key for:
![Git Bash](/images/1.Introduction/KMS/1.1.6.jpg?width=60pc) 
8. Review the Key Policy
![Git Bash](/images/1.Introduction/KMS/1.1.7-created.jpg?width=60pc) 
9. KMS key created successfull
![Git Bash](/images/1.Introduction/KMS/1.1.8.jpg?width=60pc) 

{{% notice note %}}
In the Key Policy step, you can retain the default configuration provided when the KMS key is created. We will make the necessary modifications to this part later as we continue the project.
{{% /notice %}}