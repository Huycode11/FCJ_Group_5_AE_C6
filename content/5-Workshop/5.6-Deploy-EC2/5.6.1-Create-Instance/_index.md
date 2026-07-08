---
title : "Create an EC2 Instance"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.6.1. </b> "
---

In this step, we will create an **Amazon EC2 instance** to deploy the Spring Boot Backend for the **Dental Clinic Management System**.

### Access Amazon EC2

Sign in to the **AWS Management Console**, search for **Amazon EC2**, and open the service.

From the navigation pane, choose **Instances**, then select **Launch instances** to create a new virtual server.

### Configure the Instance Name

In the **Name and tags** section, enter the following instance name:

```text
Dental-Backend
```

This name helps identify the EC2 instance used to deploy the Backend application.

### Choose an Amazon Machine Image (AMI)

Under **Application and OS Images (Amazon Machine Image)**, select:

```text
Amazon Linux 2023 AMI
```

This AMI provides a stable Linux environment for installing Docker and running the Spring Boot application.

### Choose an Instance Type

In the **Instance type** section, select:

```text
t3.micro
```

This instance type is suitable for development, testing, and workshop environments.

### Select a Key Pair

Under **Key pair (login)**, select the existing key pair:

```text
keydental
```

This key pair is required to establish an SSH connection to the EC2 instance after it is launched.

![EC2 Configuration](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/EC2p1.png)

### Configure the Security Group

In the **Network settings** section, create a new Security Group or use an existing one.

For this workshop, configure the following inbound rules:

| Type | Port | Purpose |
|------|------|---------|
| SSH | 22 | Secure Shell (SSH) access to the EC2 instance |
| HTTP | 80 | Access the application over HTTP |
| Custom TCP | 8080 | Access the Spring Boot Backend application |

Set the **Source** to:

```text
0.0.0.0/0
```

This configuration allows Internet access for demonstration and testing purposes.

![EC2 Security Group](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/EC2p2.png)

### Launch the EC2 Instance

After completing all configurations, review the **Summary** panel on the right side of the page.

If all settings are correct, choose **Launch instance**.

When the instance is successfully created, AWS displays the following message:

```text
Successfully initiated launch of instance
```

### Verify the EC2 Instance

Return to the **Instances** page to verify the status of the EC2 instance.

When the instance status changes to **Running** and the **Status check** is successful, the EC2 instance is ready to use.

![EC2 Running](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/EC2p3.png)

After completing this step, you have successfully created an Amazon EC2 instance that is ready to host the Spring Boot Backend of the **Dental Clinic Management System**.