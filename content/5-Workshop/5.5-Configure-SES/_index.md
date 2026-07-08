---
title : "Configure Amazon SES & SNS"
date : 2024-01-01
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

In the **Dental Clinic Management System**, **Amazon Simple Email Service (Amazon SES)** is used to send appointment confirmation emails and other email notifications to users, while **Amazon Simple Notification Service (Amazon SNS)** is used to manage notifications using the Publish/Subscribe messaging model.

### 1. Configure Amazon SES

Sign in to the **AWS Management Console**, search for **Amazon SES**, and navigate to **Configuration → Identities**.

Choose **Create identity**, select **Email address**, and enter the email address that will be used to send notifications from the system.

![Amazon SES Identity](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/SES.png)

After the identity has been created, AWS will send a verification email to the specified address. Open the email and choose **Verify email address** to complete the verification process.

---

### 2. Configure Amazon SNS

Sign in to the **AWS Management Console**, search for **Amazon SNS**, and select **Topics**.

Choose **Create topic**, select the **Standard** type, and enter the following topic name:

```text
dental-clinic-notification
```

Choose **Create topic** to create the SNS topic.

![Amazon SNS Topic](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/SNS.png)

After the topic is created successfully, AWS generates a **Topic ARN**, which is used by the Backend to publish notifications to Amazon SNS.

---

### 3. Configure the Backend

Update the `application.yml` file with the required AWS configuration:

```yaml
aws:
  region: ${AWS_REGION}

  ses:
    sender-email: ${AWS_SES_SENDER_EMAIL}

  sns:
    topic-arn: ${AWS_SNS_TOPIC_ARN}
```

Where:

- `AWS_REGION` specifies the AWS Region where the services are deployed.
- `AWS_SES_SENDER_EMAIL` specifies the verified email address configured in Amazon SES.
- `AWS_SNS_TOPIC_ARN` specifies the Amazon SNS Topic ARN created earlier.

After saving the configuration and restarting the Backend application, the system is ready to send email notifications through **Amazon SES** and publish notification messages through **Amazon SNS**.