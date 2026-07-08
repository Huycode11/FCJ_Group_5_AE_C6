---
title : "Configure Amazon S3"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

In the **Dental Clinic Management System**, **Amazon S3 (Simple Storage Service)** is used to store image files such as doctor avatars, service images, clinic images, and other files uploaded by users.

### 1. Create an Amazon S3 Bucket

Sign in to the **AWS Management Console**, search for **Amazon S3**, and select **Buckets**.

On the Amazon S3 dashboard, choose **Create bucket** to create a new bucket.

Configure the following settings:

- **Bucket name:** `dental-service-images-huy`
- **AWS Region:** `Asia Pacific (Singapore) - ap-southeast-1`

After completing the configuration, choose **Create bucket**.

![Amazon S3 Bucket](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/S3.png)

Once the bucket is successfully created, the **dental-service-images-huy** bucket will appear in the bucket list and is ready to be used.

---

### 2. Configure Amazon S3 in the Backend

After creating the bucket, configure the S3 settings in the Backend `application.yml` file.

```yaml
aws:
  region: ${AWS_REGION}

  s3:
    bucket-name: ${AWS_S3_BUCKET_NAME}
```

Where:

- `AWS_REGION` specifies the AWS Region where the services are deployed.
- `AWS_S3_BUCKET_NAME` specifies the name of the Amazon S3 bucket (`dental-service-images-huy`).

The Backend uses these configuration values to connect to Amazon S3 and perform operations such as uploading, downloading, and managing image files.

After completing the configuration and starting the application, the Backend can securely upload, retrieve, and manage images directly from Amazon S3.