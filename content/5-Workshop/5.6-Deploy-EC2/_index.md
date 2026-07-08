---
title : "Deploy the Backend on Amazon EC2"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

In this section, we will deploy the **Spring Boot Backend** of the **Dental Clinic Management System** to **Amazon EC2**. After the deployment is completed successfully, the Backend will connect to AWS services including **Amazon DynamoDB**, **Amazon S3**, **Amazon SES**, and **Amazon SNS** to provide the application's core features.

---

### 5.6.1. Create an EC2 Instance

Sign in to the **AWS Management Console**, search for **Amazon EC2**, and choose **Launch Instance**.

Configure the EC2 instance with the following settings:

- **Name:** Dental-Backend
- **Amazon Machine Image (AMI):** Amazon Linux 2023
- **Instance Type:** t3.micro
- **Key Pair:** Create a new key pair or use an existing one for SSH access.
- **Security Group:**
  - SSH (Port 22)
  - HTTP (Port 80)
  - Custom TCP (Port 8080)

After completing the configuration, choose **Launch Instance** to create the EC2 instance.

![Create EC2](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/EC2p3.png)

---

### 5.6.2. Connect to the EC2 Instance

Once the EC2 instance status changes to **Running**, connect to the instance using **EC2 Instance Connect** or SSH.

Example:

```bash
ssh -i keydental.pem ec2-user@<Public-IP>
```

After connecting successfully, update the operating system and install Docker to prepare the deployment environment.

---

### 5.6.3. Deploy the Backend Application

Upload the Backend source code or Docker image to the EC2 instance.

Then build and start the application using Docker:

```bash
docker build -t dental-backend .
docker run -d -p 8080:8080 --env-file .env dental-backend
```

After the application starts successfully, the Backend automatically connects to:

- Amazon DynamoDB
- Amazon S3
- Amazon SES
- Amazon SNS

These AWS services are used for database management, image storage, email delivery, and notification processing.

---

### 5.6.4. Verify the Deployment

After the deployment is complete, access the Backend using the EC2 public IP address:

```text
http://<Public-IP>:8080
```

Alternatively, use **Postman** to test the application's REST APIs.

If the Backend responds successfully, can retrieve data from **Amazon DynamoDB**, upload images to **Amazon S3**, send emails through **Amazon SES**, and publish notifications via **Amazon SNS**, the deployment has been completed successfully.