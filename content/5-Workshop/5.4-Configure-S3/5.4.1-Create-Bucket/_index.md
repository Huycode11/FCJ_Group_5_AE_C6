---
title : "Create an S3 Bucket"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.4.1. </b> "
---

In this step, we will create an **Amazon S3 Bucket** to store images for the **Dental Clinic Management System**.

### Create an Amazon S3 Bucket

1. Sign in to the **AWS Management Console**.
2. Search for **Amazon S3**.
3. Select **Buckets**.
4. Choose **Create bucket**.
5. Configure the bucket with the following settings:
   - **Bucket name:** `dental-service-images-huy`
   - **AWS Region:** `Asia Pacific (Singapore) - ap-southeast-1`
6. Keep the remaining settings as default, then choose **Create bucket**.

After the bucket is created successfully, it will appear in the list of Amazon S3 buckets.

![Amazon S3 Bucket](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/S3.png)

### Verify the Bucket

Open the **dental-service-images-huy** bucket to verify the stored objects.

The project organizes image files into separate folders based on their purposes:

- **avatars/** – Stores user profile images.
- **clinics/** – Stores clinic images.
- **services/** – Stores service images.

![Amazon S3 Objects](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/s3-objects.png)

### Verify the CloudFront Distribution

After the CloudFront distribution is created, its status will change to **Enabled**.

Copy the **Domain name** of the CloudFront distribution. This domain will be used by the Backend or Frontend to access images stored in Amazon S3.

![CloudFront Running](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/cloufront.png)

After completing this step, the system uses **Amazon CloudFront** to deliver images stored in **Amazon S3**, providing lower latency, faster content delivery, and improved application performance.

At this point, the Amazon S3 bucket is fully configured and ready for the Backend to upload, store, and retrieve image files used by the Dental Clinic Management System.