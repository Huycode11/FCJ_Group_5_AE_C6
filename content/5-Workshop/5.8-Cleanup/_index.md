---
title : "Clean Up Resources"
date : 2024-01-01
weight : 8
chapter : false
pre : " <b> 5.8. </b> "
---

After completing the workshop and verifying that the system is functioning correctly, the final step is to clean up the AWS resources to avoid unnecessary charges.

In this section, we will review how to remove the AWS resources used during the deployment of the **Dental Clinic Management System**.

### 5.8.1. Delete the Amazon EC2 Instance

1. Open the **Amazon EC2 Console**.
2. Choose **Instances**.
3. Select the EC2 instance created for the project.
4. Choose **Instance state → Terminate instance**.
5. Confirm the termination.

![Terminate EC2](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/xoaEC2.png)

---

### 5.8.2. Delete the Amazon S3 Bucket

1. Open the **Amazon S3 Console**.
2. Select the project bucket.
3. Delete all objects stored in the bucket.
4. Choose **Delete bucket**.
5. Enter the bucket name to confirm the deletion.

> **Note:** In this workshop, the team **does not delete the Amazon S3 bucket** because it is still being used to store application images for future development, testing, and demonstrations.

---

### 5.8.3. Delete Amazon DynamoDB Tables

1. Open the **Amazon DynamoDB Console**.
2. Choose **Tables**.
3. Select the project tables, including:
   - users
   - doctors
   - services
   - appointments
   - invoices
   - feedbacks
   - consultations
   - clinics
4. Choose **Delete table**.
5. Confirm the deletion.

> **Note:** In this workshop, the team **does not delete the Amazon DynamoDB tables** because the data is still required for development, testing, and demonstration purposes.

---

### 5.8.4. Delete the Amazon SNS Topic

1. Open the **Amazon SNS Console**.
2. Choose **Topics**.
3. Select the SNS topic created for the project.
4. Choose **Delete**.
5. Confirm the deletion.

> **Note:** In this workshop, the team **does not delete the Amazon SNS topic** because it is still used to send notification emails during testing and future development.

---

### 5.8.5. Delete the Amazon SES Identity

1. Open the **Amazon SES Console**.
2. Navigate to **Configuration → Identities**.
3. Select the verified email identity.
4. Choose **Delete**.

> **Note:** In this workshop, the team **does not delete the Amazon SES identity** because it is still used to send appointment confirmation emails and system notifications.

---

After completing these steps, all AWS resources that are no longer required can be removed to prevent unnecessary charges.

Resources that are still needed for future development and testing, such as **Amazon S3**, **Amazon DynamoDB**, **Amazon SNS**, and **Amazon SES**, are intentionally retained.