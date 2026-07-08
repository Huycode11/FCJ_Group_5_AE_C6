---

title : "Configure DynamoDB"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
-----------------------

In this step, we will check the **Amazon DynamoDB** tables used in the **Dental Clinic Management System**.

Sign in to the **AWS Management Console**, search for the **DynamoDB** service, and select **Tables**.

Here, the system's data tables have already been created and are ready to use.

The main tables of the system include:

| Table            | Function                       |
| ---------------- | ------------------------------ |
| users            | Store user account information |
| doctors          | Store doctor information       |
| specialties      | Store specialty information    |
| services         | Store service information      |
| appointments     | Store appointment information  |
| doctor_schedules | Store doctors' work schedules  |
| consultations    | Store consultation requests    |
| invoices         | Store invoice information      |
| feedbacks        | Store patient feedback         |
| blogs            | Store blog posts               |
| categories       | Store blog categories          |
| clinics          | Store clinic information       |

![DynamoDB Tables](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/dynamodb-tables.png)

Check the status of the tables and ensure that all of them are in the **Active** state before continuing with the system deployment.
