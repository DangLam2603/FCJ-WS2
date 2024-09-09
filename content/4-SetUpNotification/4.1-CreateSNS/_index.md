---
title : "Create SNS"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

## Create SNS to send email
In this section, we will config a Email service using SNS topic.

#### Create Topic
1. Navigate to **AWS console**, Search for **SNS** sevice.
![SNS](/images/4.Notification/SNS/4.1.1-sns.jpg?width=60pc)

2. Select **Create a Topic**.
![SNS](/images/4.Notification/SNS/4.1.2-topic.jpg?width=60pc)

3. In the Detail section, select **Standard** type and paste ```guardduty-topic``` in the **name** part.
![SNS](/images/4.Notification/SNS/4.1.3.jpg?width=60pc)

4. Then, Click **Create Topic**
![SNS](/images/4.Notification/SNS/4.1.4.jpg?width=60pc)

#### Create and Subscribe subscription

1. Navigate to left sidebar and select **Topic**:
   - Choose the following topic that we just created
   - the select **subscription** and click **create subscription**  
![SNS](/images/4.Notification/SNS/4.1.5-subscription.jpg?width=60pc)
2. In the Details section, select **Email** on the **Protocol** part
![SNS](/images/4.Notification/SNS/4.1.6.jpg?width=60pc)
3. Next, specify the **email** that will recieve the notification from SNS 
![SNS](/images/4.Notification/SNS/4.1.7.jpg?width=60pc)
4. Click **Create Subscription**
![SNS](/images/4.Notification/SNS/4.1.8.jpg?width=60pc)
5. Completed create subscription.
![SNS](/images/4.Notification/SNS/4.1.9.jpg?width=60pc)
{{% notice info %}}
After you create subscription, the following status will be pending to confirm. You will recieve a confirmation email base on the one you provide above.
{{% /notice %}} 
![SNS](/images/4.Notification/SNS/4.1.10.jpg?width=60pc)
#### Confirm Email
1. Email Confirm successully.
![SNS](/images/4.Notification/SNS/4.1.11.jpg?width=60pc)
2. Status Update
![SNS](/images/4.Notification/SNS/4.1.12.jpg?width=60pc)