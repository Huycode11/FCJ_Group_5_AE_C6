---
title : "Introduction"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### System Introduction

The **Dental Clinic Management System** is a cloud-based web application designed to streamline dental clinic operations and provide patients with a convenient online appointment booking experience. The system enables patients to register, log in, browse available dental services, view dentist information, schedule appointments, and track appointment status. In addition, administrators can efficiently manage dentists, services, patients, and appointments through a centralized management portal.

The application is developed using a **3-Tier Architecture**, separating the Presentation Layer (Frontend), Application Layer (Backend), and Data Layer (Database). This architecture improves scalability, maintainability, security, and overall system performance while making it easier to manage and expand future functionalities.

#### Workshop Overview

This workshop demonstrates how to deploy the **Dental Clinic Management System** on **Amazon Web Services (AWS)** using multiple AWS services to build a secure, scalable, and highly available cloud-native application.

The workshop covers the deployment and configuration of the following AWS services:

- **AWS Amplify** is used to host and deploy the ReactJS frontend application.
- **Amazon CloudFront** delivers static content globally with low latency, while **Amazon Route 53** manages DNS and domain routing.
- **AWS WAF** protects the application from common web attacks such as SQL Injection (SQLi) and Cross-Site Scripting (XSS).
- **Amazon EC2** hosts the Spring Boot backend application and processes business logic through RESTful APIs.
- **Application Load Balancer (ALB)** distributes incoming traffic to improve application availability and scalability.
- **Amazon DynamoDB** stores application data, including user accounts, dentists, services, and appointment information.
- **Amazon S3** stores static assets, uploaded images, and supporting documents.
- **AWS Identity and Access Management (IAM)** manages authentication and authorization for AWS resources.
- **AWS Secrets Manager** securely stores sensitive credentials and application secrets.
- **AWS Key Management Service (AWS KMS)** encrypts sensitive data and manages encryption keys.
- **Amazon CloudWatch** monitors system performance, collects logs, and provides operational insights.
- **Amazon SNS** delivers system notifications, while **Amazon SES** sends appointment confirmation and notification emails to users.

By following this workshop, readers will learn how to prepare the AWS environment, deploy both frontend and backend applications, configure database and storage services, implement security best practices, monitor system performance, and perform resource cleanup after deployment.

![AWS Architecture](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/drawio.png)

### System Workflow

1. **Users/Doctors** access the website through the domain managed by **Amazon Route 53**.

2. **Amazon Route 53** routes incoming requests to **Amazon CloudFront**, providing faster content delivery and low-latency access.

3. **AWS WAF** inspects and filters incoming requests before they reach CloudFront, protecting the application against threats such as SQL Injection (SQLi), Cross-Site Scripting (XSS), and abnormal traffic.

4. **Amazon CloudFront** delivers the ReactJS frontend hosted on **AWS Amplify** and serves static assets stored in **Amazon S3**.

5. When users perform operations such as logging in, booking appointments, or accessing application features, the **Frontend (AWS Amplify)** sends API requests to the **Application Load Balancer (ALB)**.

6. **Application Load Balancer (ALB)** forwards incoming requests to the **Amazon EC2** instance running the Spring Boot backend application.

7. **Amazon EC2** processes business logic, including user authentication, doctor management, service management, appointment scheduling, and other backend operations.

8. During request processing, **Amazon EC2** stores and retrieves images from **Amazon S3**, and uses **Amazon SES** and **Amazon SNS** to send email notifications and system alerts when required.

9. Finally, **Amazon EC2** reads and writes application data to **Amazon DynamoDB**. At the same time, **Amazon CloudWatch** monitors system performance and triggers notifications through **Amazon SNS** whenever configured thresholds or alarms are reached.
