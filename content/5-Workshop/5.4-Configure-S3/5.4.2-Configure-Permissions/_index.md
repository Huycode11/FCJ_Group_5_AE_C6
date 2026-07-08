---
title : "Configure Access Permissions"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.4.2. </b> "
---

In the **Dental Clinic Management System**, protecting image files (such as doctor profile photos and patient-related images) is an important security requirement. Therefore, the system does **not** allow public access to objects stored in Amazon S3. Instead, access is granted dynamically through the Backend.

### 1. Bucket Security Policy

During the bucket creation process, the default setting **Block all public access** was kept enabled.

This means that no one on the Internet can directly access or download images from Amazon S3 using the original object URL. If an attempt is made, Amazon S3 returns an **Access Denied** error.

Only the Backend application, using the IAM user **`dental-backend-user`** with the **AmazonS3FullAccess** policy, is authorized to read from and write files to the S3 bucket.

### 2. Granting Access with Pre-signed URLs

To allow the ReactJS Frontend to display images securely, the Spring Boot Backend acts as an intermediary by generating **pre-signed URLs**.

A pre-signed URL is a temporary, signed link that grants time-limited access to a specific object stored in Amazon S3 without making the bucket publicly accessible.

In the Backend source code, the `AwsConfig` class defines an `S3Presigner` bean as shown below:

```java
@Bean
public S3Presigner s3Presigner(AwsCredentialsProvider credentialsProvider) {
    return S3Presigner.builder()
            .region(Region.of(region))
            .credentialsProvider(credentialsProvider)
            .build();
}
```

