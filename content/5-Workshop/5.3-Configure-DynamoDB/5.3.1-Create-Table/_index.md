---
title : "Create DynamoDB Table"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.3.1. </b> "
---

---

title : "Create DynamoDB Tables"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.3.1. </b> "
-------------------------

In the **Dental Clinic Management System**, **Amazon DynamoDB** tables are **not created manually** through the AWS Management Console. Instead, they are automatically initialized by the Spring Boot Backend application during startup.

The Backend uses the `DynamoDbTableInitializer` class to check whether the required tables exist and create them if they do not.

```java
@Configuration
public class DynamoDbTableInitializer {

    private final DynamoDbEnhancedClient enhancedClient;

    public DynamoDbTableInitializer(DynamoDbEnhancedClient enhancedClient) {
        this.enhancedClient = enhancedClient;
    }

    @PostConstruct
    public void createTables() {
        createTableIfNotExists("users", User.class);
        createTableIfNotExists("invoices", Invoice.class);
        createTableIfNotExists("feedbacks", Feedback.class);
        createTableIfNotExists("doctor_schedules", DoctorSchedule.class);
        createTableIfNotExists("doctors", Doctor.class);
        createTableIfNotExists("services", DentalService.class);
        createTableIfNotExists("consultations", Consultation.class);
        createTableIfNotExists("blogs", Blog.class);
        createTableIfNotExists("appointments", Appointment.class);
        createTableIfNotExists("categories", Category.class);
        createTableIfNotExists("specialties", Specialty.class);
        createTableIfNotExists("clinics", Clinic.class);
    }
}
```

When the Spring Boot application starts, the `@PostConstruct` annotation automatically invokes the `createTables()` method. This method checks whether each DynamoDB table already exists and creates it if necessary.

The following DynamoDB tables are created automatically:

| Table            | Description                       |
| ---------------- | --------------------------------- |
| users            | Stores user account information   |
| invoices         | Stores invoice information        |
| feedbacks        | Stores patient feedback           |
| doctor_schedules | Stores doctors' work schedules    |
| doctors          | Stores doctor information         |
| services         | Stores dental service information |
| consultations    | Stores consultation requests      |
| blogs            | Stores blog articles              |
| appointments     | Stores appointment information    |
| categories       | Stores blog categories            |
| specialties      | Stores dental specialties         |
| clinics          | Stores clinic information         |

After the application starts successfully, navigate to **AWS Management Console → DynamoDB → Tables** to verify that the tables have been created.

![DynamoDB Tables](/FCJ_Group_5_AE_C6/images/5-Workshop/5.1-Workshop-overview/dynamodb-tables.png)

If all tables are displayed with the **Active** status, the DynamoDB table initialization process has completed successfully.
