---
title : "Create Event for GuardDuty"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

### Overview
In this section, we will implement an event-driven architecture to monitor findings from Amazon GuardDuty in real time. Using Amazon EventBridge, we will create rules that trigger specific actions whenever GuardDuty detects potential threats or vulnerabilities

1. In the AWS search bar, type **EventBridge** and select the first one.
![EventBridge](/images/4.Notification/EventBridge/4.2.1-started.jpg?width=60pc)

2. Switch to the **EventBridge Rule** tab and click **Create Rule**
![EventBridge](/images/4.Notification/EventBridge/4.2.2.jpg?width=60pc)

3. Type ```rule-event-gd``` for the Name section, and leave the default option for the rest
![EventBridge](/images/4.Notification/EventBridge/4.2.3.jpg?width=60pc)

4. On the **Event Pattern**, select the following
   - **Event Source**, Select **AWS service**
   - Choose **GuardDuty** for **AWS service**
   - **GuardDuty Findings** for the **event type**.

Then, choose the **Edit Pattern** to change the servity of the event will be triggered.
![EventBridge](/images/4.Notification/EventBridge/4.2.5.jpg?width=60pc)

5. Paste the following and modify the dangerous level of the findings
```
{
  "source": [
    "aws.guardduty"
  ],
  "detail-type": [
    "GuardDuty Finding"
  ],
  "detail": {
    "severity": [
      4,
      4.0,
      4.1,
      4.2,
      4.3,
      4.4,
      4.5,
      4.6,
      4.7,
      4.8,
      4.9,
      5,
      5.0,
      5.1,
      5.2,
      5.3,
      5.4,
      5.5,
      5.6,
      5.7,
      5.8,
      5.9,
      6,
      6.0,
      6.1,
      6.2,
      6.3,
      6.4,
      6.5,
      6.6,
      6.7,
      6.8,
      6.9,
      7,
      7.0,
      7.1,
      7.2,
      7.3,
      7.4,
      7.5,
      7.6,
      7.7,
      7.8,
      7.9,
      8,
      8.0,
      8.1,
      8.2,
      8.3,
      8.4,
      8.5,
      8.6,
      8.7,
      8.8,
      8.9
    ]
  }
}
```
![EventBridge](/images/4.Notification/EventBridge/4.2.6.jpg?width=60pc)
6. In the Advance Settings, Select the below:
   - Choose AWS service
   - Select SNS topic
   - and in the Topic part, choose the ```guardduty-topic```, that you just created
![EventBridge](/images/4.Notification/EventBridge/4.2.7.jpg?width=60pc)  
7. Next, we will create a custom notification for SNS:
 - In the **additional settings**, select **Input transformer**
![EventBridge](/images/4.Notification/EventBridge/4.2.8.jpg?width=60pc)
8. In the **Target input transforme**r, Type the following **Input Path**:
```
{
    "severity": "$.detail.severity",
    "Account_ID": "$.detail.accountId",
    "Finding_ID": "$.detail.id",
    "Finding_Type": "$.detail.type",
    "region": "$.region",
    "Finding_description": "$.detail.description"
}
                            
```
![EventBridge](/images/4.Notification/EventBridge/4.2.9.jpg?width=60pc)
9. On the **Template**, we will procvide the following **Input Template:**
```
"AWS <Account_ID> has a severity <severity> GuardDuty finding type <Finding_Type> in the <region> region."
"Finding Description:"
"<Finding_description>. "
"For more details open the GuardDuty console at https://console.aws.amazon.com/guardduty/home?region=<region>#/findings?search=id%3D<Finding_ID>"                         
```
![EventBridge](/images/4.Notification/EventBridge/4.2.10.jpg?width=60pc)
10. Review and click Create rule
![EventBridge](/images/4.Notification/EventBridge/4.2.12.jpg?width=60pc)
11. Complete create event rule.
![EventBridge](/images/4.Notification/EventBridge/4.2.13.jpg?width=60pc)