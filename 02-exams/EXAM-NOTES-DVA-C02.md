# Exam notes AWS SOA-C02

## HTTP Status

|                         |     |     |                       |      | S3                                        |     |     |
| ----------------------- | --- | --- | --------------------- | ---- | ----------------------------------------- | --- | --- |
| Informational responses | 1xx | 100 | Continue              | ⏩   |                                           |     |     |
|                         |     |     |                       |      |                                           |     |     |
| Successful responses    | 2xx | 200 | OK                    | ✅   |                                           |     |     |
|                         |     | 201 | Created               | 🆕   |                                           |     |     |
|                         |     | 202 | Accepted              | 🤝   |                                           |     |     |
|                         |     |     |                       |      |                                           |     |     |
| Redirection messages    | 3xx | 300 | Multiple Choices      | 👯   |                                           |     |     |
|                         |     | 301 | Moved Permanently     | 🚐   |                                           |     |     |
|                         |     |     |                       |      |                                           |     |     |
|                         |     | 307 | Temporary Redirect    | 🔂   |                                           |     |     |
|                         |     | 308 | Permanent Redirect    | 🔁   |                                           |     |     |
|                         |     |     |                       |      |                                           |     |     |
| Client error responses  | 4xx | 400 | Bad Request           | ❌   |                                           |     |     |
|                         |     | 401 | Unauthorized          | 🪪   |                                           |     |     |
|                         |     |     |                       |      |                                           |     |     |
|                         |     | 403 | Forbidden             | 🚫   |                                           |     |     |
|                         |     | 404 | Not Found             | 🕵️‍♂️   |                                           |     |     |
|                         |     |     |                       |      |                                           |     |     |
|                         |     | 429 | Too Many Requests     | 💤   |                                           |     |     |
|                         |     |     |                       |      |                                           |     |     |
| Server error responses  | 5xx | 500 | Internal Server Error | 🚨   |                                           |     |     |
|                         |     | 501 | Not Implemented       | 🏗️   |                                           |     |     |
|                         |     | 502 | Bad Gateway           | ❌   |                                           |     |     |
|                         |     | 503 | Service Unavailable   | 🚧📈 | Object with millions of versions [S3.503] |     |     |
|                         |     | 504 | Gateway Timeout       | ⏳   |                                           |     |     |
|                         |     |     |                       |      |                                           |     |     |

[S3.503]: https://docs.aws.amazon.com/AmazonS3/latest/userguide/troubleshooting-versioning.html#performance-degradation

### Database replication

|                  | RDS Multi-AZ Instance | RDS Multi-AZ Cluster                | [RDS Read Replicas] | Aurora Read Replicas |
| ---------------- | --------------------- | ----------------------------------- | ------------------- | -------------------- |
| Main purpose     | **High Availability** | **High Availability** + Scalability | **Scalability**     | **Scalability**      |
| Data replication | **Synchronously**     | Asynchronously                      | Asynchronously      | Asynchronously       |

|                  | [RDS Cross-Region Read Replicas]    | [Aurora Cross-Region Read Replicas] | [Aurora Global Database]                | [DynamoDB Global Table]                 |
| ---------------- | ----------------------------------- | ----------------------------------- | --------------------------------------- | --------------------------------------- |
| Main purpose     | **Disaster Recovery** + Scalability | **Disaster Recovery** + Scalability | ??? Disaster Recovery + **Scalability** | ??? Disaster Recovery + **Scalability** |
| Data replication | Asynchronously                      | Asynchronously                      | ??? Asynchronously (within a second)    |                                         |

[RDS Read Replicas]: https://aws.amazon.com/rds/features/read-replicas/
[RDS Cross-Region Read Replicas]: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html#USER_ReadRepl.XRgn
[Aurora Cross-Region Read Replicas]: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraMySQL.Replication.CrossRegion.html
[Aurora Global Database]: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database.html
[DynamoDB Global Table]: https://aws.amazon.com/dynamodb/global-tables/

### Encryption at rest

- EBS:
  - By default, an EBS volume is not encrypted when created
    - while creating an EC2 instance.
    - standalone.
  - EBS encryption can be enable at region-level (by using EBS `encryption by default`)[^ebs-1]

[^ebs-1]: <https://aws.amazon.com/blogs/aws/new-opt-in-to-default-encryption-for-new-ebs-volumes/>
