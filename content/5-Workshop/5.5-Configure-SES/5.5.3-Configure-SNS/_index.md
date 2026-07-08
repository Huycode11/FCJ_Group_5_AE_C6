---
title : "Configure SNS Notifications"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.5.3. </b> "
---

In this section, we will configure **Amazon Simple Notification Service (Amazon SNS)** to automatically send email notifications, such as system alerts and reports, to a Gmail account.

### 1. Create an SNS Topic

1. Sign in to the **AWS Management Console**, search for **Amazon SNS**, and select **Topics**.
2. Choose **Create topic**.
3. For **Type**, select **Standard**.
4. Enter a **Name** for the topic (for example: `dental-system-alerts`).
5. Keep the remaining settings as default, then choose **Create topic**.

---

### 2. Subscribe a Gmail Address

After the topic has been created, add an email address to receive notifications.

1. Open the newly created topic and navigate to the **Subscriptions** tab.
2. Choose **Create subscription**.
3. For **Protocol**, select **Email**.
4. For **Endpoint**, enter your Gmail address (for example: `your-email@gmail.com`).
5. Choose **Create subscription**.

---

### 3. Confirm the Subscription

1. Amazon SNS will send a confirmation email to the Gmail address you provided.
2. Open your Gmail inbox and locate the email titled **AWS Notification - Subscription Confirmation**.
3. Choose **Confirm subscription** by clicking the confirmation link in the email.
4. Return to the AWS Management Console and verify that the subscription status has changed from **Pending confirmation** to **Confirmed**.

---

### 4. Publish a Test Message

1. Open the SNS topic in the AWS Management Console and choose **Publish message**.
2. Enter a **Subject** (for example: `Dental Clinic System Test Alert`).
3. Enter the message in the **Message body to send to the endpoint** field (for example: `The Dental Clinic Management System is operating normally.`).
4. Scroll to the bottom of the page and choose **Publish message**.
5. Check your Gmail inbox to verify that the notification email has been received.

After completing these steps, Amazon SNS is fully configured and ready to be integrated with **Amazon CloudWatch** or the **Spring Boot Backend** to automatically deliver email notifications.