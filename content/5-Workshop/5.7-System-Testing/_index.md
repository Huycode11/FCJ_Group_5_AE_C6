---
title : "System Verification"
date : 2024-01-01
weight : 7
chapter : false
pre : " <b> 5.7. </b> "
---

After deploying the **Dental Clinic Management System** to AWS, the final step is to verify that all AWS services are functioning correctly and communicating with each other.

In this section, we will verify that the Spring Boot Backend running on **Amazon EC2** can successfully connect to **Amazon DynamoDB**, **Amazon S3**, **Amazon SES**, and **Amazon SNS**, and ensure that the core features of the system are working as expected.

### 5.7.1. Verify the EC2 Instance

First, open the **Amazon EC2 Console** and check the status of the EC2 instance.

If the instance status is **Running** and all **Status Checks** have passed, the server is ready to host the Backend application.

![EC2 Running](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/EC2p3.png)

---

### 5.7.2. Verify Data Storage

Sign in to the application and create or update data.

Then open **Amazon DynamoDB** and verify that the data has been successfully stored in the corresponding tables.

![DynamoDB](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/database.png)

---

### 5.7.3. Verify Image Upload

Upload a profile image or a service image through the application.

After the upload is completed, open the **Amazon S3** bucket and verify that the image file has been stored successfully.

![Amazon S3](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/s3avata.png)

---

### 5.7.4. Verify Email Delivery

Create a new appointment or trigger the email notification feature from the application.

If the user receives the notification email in Gmail, it confirms that **Amazon SES** has been configured correctly and is functioning as expected.

![Amazon SES](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/nhangmail.png)

---

### 5.7.5. Verify Amazon SNS Notifications

Publish a test message to the configured **Amazon SNS** topic or trigger an event that sends a notification.

If the subscribed email address receives the notification successfully, it confirms that Amazon SNS is working properly and can deliver notification messages.

---

After completing all the verification steps, the **Dental Clinic Management System** has been successfully deployed on the AWS Cloud.

The Spring Boot Backend is running successfully on **Amazon EC2** and is fully integrated with **Amazon DynamoDB**, **Amazon S3**, **Amazon SES**, and **Amazon SNS**, enabling the application to provide secure data storage, image management, email delivery, and notification services.