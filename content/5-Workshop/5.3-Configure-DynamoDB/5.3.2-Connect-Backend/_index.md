---
title : "Connect Backend"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.3.2. </b> "
---

In this section, we will configure the Spring Boot Backend to securely connect to **Amazon DynamoDB** using the **AWS SDK for Java**.

### 1. Configure AWS Credentials

To allow the Backend application to access Amazon DynamoDB, AWS credentials (Access Key ID and Secret Access Key) must be provided.

Instead of hardcoding these values in the source code, the project reads them from **environment variables** through the `application.yml` configuration file:

```yaml
aws:
  credentials:
    access-key-id: ${AWS_ACCESS_KEY_ID}
    secret-access-key: ${AWS_SECRET_ACCESS_KEY}
  region: ${AWS_REGION}
```

Using environment variables helps improve security and makes the application easier to deploy across different environments.

### 2. Verify the DynamoDB Connection

After configuring the AWS credentials, start the Spring Boot Backend with the following command:

```bash
mvn spring-boot:run
```

When the application starts, the `DynamoDbTableInitializer` class automatically checks whether the required DynamoDB tables already exist. If a table exists, the following message is displayed:

```text
Checking and creating DynamoDB tables if they do not exist...
Table already exists: users
Table already exists: invoices
Table already exists: feedbacks
Table already exists: doctor_schedules
Table already exists: doctors
Table already exists: services
Table already exists: consultations
Table already exists: blogs
Table already exists: appointments
Table already exists: categories
Table already exists: specialties
Table already exists: clinics
```

The terminal output confirms that the Backend has successfully connected to Amazon DynamoDB and verified the required tables.

![DynamoDB Tables](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/connetdb.png)

The log messages above indicate that the Backend application can successfully access Amazon DynamoDB and validate the required database tables for the Dental Clinic Management System.