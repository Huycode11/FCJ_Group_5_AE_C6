---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Deploying the Dental Clinic Management System on AWS

#### Overview

In this workshop, we will walk through the deployment of the **Dental Clinic Management System** on the **Amazon Web Services (AWS)** cloud platform.

The project was developed to address the limitations of traditional dental clinic management, including:

- Managing appointments using paper records or spreadsheets, which can lead to scheduling conflicts and data loss.
- Patients having to call or visit the clinic in person to book appointments, resulting in inconvenience for both patients and staff.
- Difficulty managing doctors, services, appointments, and patient information within a single system.
- Limited monitoring and visibility into system performance as the number of users increases.
- Challenges in scaling and maintaining applications hosted on traditional on-premises infrastructure.

To overcome these challenges, the system is designed using a **3-Tier Architecture**, with **ReactJS** as the Frontend, **Spring Boot** as the Backend, and **Amazon DynamoDB** as the NoSQL database.

Deploying the application on AWS provides scalability, high availability, enhanced security, and reduced infrastructure management overhead.

Throughout this workshop, you will learn how to deploy the complete application on AWS, including preparing the environment, deploying the Frontend and Backend, configuring the database, integrating storage and notification services, deploying the application on Amazon EC2, verifying the system, and cleaning up AWS resources.

The AWS services used in this workshop include:

- Amazon EC2
- AWS Amplify
- Amazon DynamoDB
- Amazon S3
- Amazon CloudFront
- Amazon Route 53
- AWS WAF
- AWS Secrets Manager
- AWS Key Management Service (AWS KMS)
- Amazon CloudWatch
- Amazon Simple Notification Service (Amazon SNS)
- Amazon Simple Email Service (Amazon SES)
- AWS Identity and Access Management (IAM)

#### Contents

1. [Introduction](5.1-Workshop-overview/)
2. [Prerequisites](5.2-Prerequiste/)
3. [Configure Amazon DynamoDB](5.3-Configure-DynamoDB/)
4. [Configure Amazon S3](5.4-Configure-S3/)
5. [Configure Amazon SES & SNS](5.5-Configure-SES/)
6. [Deploy the Backend on Amazon EC2](5.6-Deploy-EC2/)
7. [System Verification](5.7-System-Testing/)
8. [Clean Up Resources](5.8-Cleanup/)