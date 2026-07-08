---
title : "Verify Email Subscription"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.5.1. </b> "
---

In this section, we will configure **Amazon Simple Notification Service (Amazon SNS)** to send notifications from the **Dental Clinic Management System** through an SNS topic.

### 1. Create an SNS Topic

Sign in to the **AWS Management Console**, search for **Amazon SNS**, and select **Topics**.

Choose **Create topic** and configure the following settings:

- **Type:** Standard
- **Name:** `dental-clinic-notification`

Keep the remaining settings as default, then choose **Create topic**.

---

### 2. Create an Email Subscription

After the topic has been created, register an email address to receive notifications.

1. Open the SNS topic you created.
2. Choose **Create subscription**.
3. For **Protocol**, select **Email**.
4. For **Endpoint**, enter the email address that will receive notifications.
5. Choose **Create subscription**.

---

### 3. Confirm the Subscription

Amazon SNS will send a confirmation email to the registered email address.

Open the email and choose **Confirm subscription** to complete the subscription process.

Once the subscription has been confirmed successfully, its status will change to **Confirmed**.

---

### 4. Test Notification Delivery

From the SNS topic page, choose **Publish message**.

Enter the following test information:

- **Subject:** Dental Clinic Notification
- **Message:** Test notification from Dental Clinic Management System.

Then choose **Publish message**.

If the configuration is successful, the subscribed email address will receive the notification sent through Amazon SNS.

At this point, Amazon SNS is fully configured and ready to be integrated with the Backend to deliver notifications for the **Dental Clinic Management System**.