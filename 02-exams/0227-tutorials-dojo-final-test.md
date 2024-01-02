# Tutorial Dojo - SOA-C02 - Final Test

Test time: 00:45:07

Score: 59/65 (90%):

|          | Domain                                   | Score | Percent |
| -------- | ---------------------------------------- | ----- | ------- |
| Domain 1 | Monitoring, Logging, and Remediation     | 8/10  | 80%     |
| Domain 2 | Reliability and Business Continuity      | 10/11 | 90.91%  |
| Domain 3 | Deployment, Provisioning, and Automation | 14/15 | 93.33%  |
| Domain 4 | Security and Compliance                  | 14/15 | 93.33%  |
| Domain 5 | Networking and Content Delivery          | 5/6   | 83.33%  |
| Domain 6 | Cost and Performance Optimization        | 8/8   | 100%    |

## Domain 1: Monitoring, Logging, and Remediation

| No  |     | Q                                                                       | A                                                                                       | Ref |
| --- | --- | ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --- |
|     |     |                                                                         |                                                                                         |     |
| 1   |     |                                                                         |                                                                                         |     |
| 2   |     |                                                                         |                                                                                         |     |
| 3   | ❌  | EC2 + ALB + RDS: 90% CPU of EC2, 20% CPU of RDS. Improve response time? | 1. 90% CPU -> ASG (EC2); 2. Switch to a EC2 instance type with greater CPU/memory ratio |     |
| 4   | ❌  | ELB: Health check?                                                      | [AWS services with health check](#14-aws-services-with-health-check)                    |     |
| 5   |     |                                                                         |                                                                                         |     |
| 6   |     |                                                                         |                                                                                         |     |
| 7   |     |                                                                         |                                                                                         |     |
| 8   |     |                                                                         |                                                                                         |     |
| 9   |     |                                                                         |                                                                                         |     |
| 10  |     |                                                                         |                                                                                         |     |

## Domain 2: Reliability and Business Continuity

| No  |     | Q                               | A                                                             | Ref |
| --- | --- | ------------------------------- | ------------------------------------------------------------- | --- |
|     |     |                                 |                                                               |     |
| 1   |     |                                 |                                                               |     |
| 2   | ❌  | RDS: Reduce failover time (HA)? | RDS HA options:[^2.2.1] 1. RDS Proxy; 2. RDS Multi-AZ[^2.2.2] |     |
| 3   |     |                                 |                                                               |     |
| 4   |     |                                 |                                                               |     |
| 5   |     |                                 |                                                               |     |
| 6   |     |                                 |                                                               |     |
| 7   |     |                                 |                                                               |     |
| 8   |     |                                 |                                                               |     |
| 9   |     |                                 |                                                               |     |
| 10  |     |                                 |                                                               |     |
| 11  |     |                                 |                                                               |     |

## Domain 3: Deployment, Provisioning, and Automation

| No  |     | Q                                                          | A                                                                                                        | Ref |
| --- | --- | ---------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | --- |
|     |     |                                                            |                                                                                                          |     |
| 1   |     |                                                            |                                                                                                          |     |
| 2   |     |                                                            |                                                                                                          |     |
| 3   |     |                                                            |                                                                                                          |     |
| 4   |     |                                                            |                                                                                                          |     |
| 5   |     |                                                            |                                                                                                          |     |
| 6   |     |                                                            |                                                                                                          |     |
| 7   |     |                                                            |                                                                                                          |     |
| 8   | ❌  | EC2: MongoDB + nginx: 200.000 IOPS in 4kB random I/O. How? | 1. Storage Optimized Instance[^3.8.1] (very fast instance store); 2. Provisional IOPS EBS Volume[^3.8.2] |     |
| 9   |     |                                                            |                                                                                                          |     |
| 10  |     |                                                            |                                                                                                          |     |
| 11  |     |                                                            |                                                                                                          |     |
| 12  |     |                                                            |                                                                                                          |     |
| 13  |     |                                                            |                                                                                                          |     |
| 14  |     |                                                            |                                                                                                          |     |
| 15  |     |                                                            |                                                                                                          |     |

## Domain 4: Security and Compliance

| No  |     | Q                                                                       | A                                                                                                                                                                              | Ref |
| --- | --- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --- |
|     |     |                                                                         |                                                                                                                                                                                |     |
| 1   |     |                                                                         |                                                                                                                                                                                |     |
| 2   |     |                                                                         |                                                                                                                                                                                |     |
| 3   |     |                                                                         |                                                                                                                                                                                |     |
| 4   |     |                                                                         |                                                                                                                                                                                |     |
| 5   |     |                                                                         |                                                                                                                                                                                |     |
| 6   | ❌  | IAM Policy: Action `s3:GetObject` + resource `arn:aws:s3:::bucket_name` | "Action does not apply to any resource(s) in statement". (The `s3:GetObject` expects objects in the bucket, e.g. `arn:aws:s3:::bucket_name/key_name`, `bucket_Name/*`[^4.6.1]) |     |
| 7   |     |                                                                         |                                                                                                                                                                                |     |
| 8   |     |                                                                         |                                                                                                                                                                                |     |
| 9   |     |                                                                         |                                                                                                                                                                                |     |
| 10  |     |                                                                         |                                                                                                                                                                                |     |
| 11  |     |                                                                         |                                                                                                                                                                                |     |
| 12  |     |                                                                         |                                                                                                                                                                                |     |
| 13  |     |                                                                         |                                                                                                                                                                                |     |
| 14  |     |                                                                         |                                                                                                                                                                                |     |
| 15  |     |                                                                         |                                                                                                                                                                                |     |

## Domain 5: Networking and Content Delivery

| No  |     | Q               | A                              | Ref |
| --- | --- | --------------- | ------------------------------ | --- |
|     |     |                 |                                |     |
| 1   |     |                 |                                |     |
| 2   | ❌  | VPC Route table | [Route table](#52-route-table) |     |
| 3   |     |                 |                                |     |
| 4   |     |                 |                                |     |
| 5   |     |                 |                                |     |
| 6   |     |                 |                                |     |

## Domain 6: Cost and Performance Optimization

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   |     |     |     |     |
| 2   |     |     |     |     |
| 3   |     |     |     |     |
| 4   |     |     |     |     |
| 5   |     |     |     |     |
| 6   |     |     |     |     |
| 7   |     |     |     |     |
| 8   |     |     |     |     |

## 1.4 AWS services with health check

### Elastic Load Balancer

ELB: load balancer routes requests to the `targets` in a `target group` and performs health checks on the targets.[^1.4.1]

- Target groups:

  - Target type:

    - Instances
    - IP Addresses
    - Lambda function
    - ALB

  - Health check
    - Protocol: HTTP/HTTPS
    - Path

### Route 53

Route 53 supports 3 type of health checks:

1. Check an endpoint

   Route 53 health checks monitor the health and performance of your application's servers, or endpoints, from a network of health checkers in locations around the world.

   To create an endpoint health check:

   - For non-alias record, you specify:

     - a domain name/an IP address
     - a port
     - protocol (HTTP, HTTPS, TCP)

   - For alias record, you set the value of `Evaluate Target Health` to `Yes`

     - The endpoint can even be an ELB[^1.4.2]

2. Check check health check

3. Check a CW alarm

## 5.2 Route table

Route table concepts:[^5.2.1]

- `Route table`

- `Route`

  - `Destination`: Range of IPs (CIDR block) ("**_Which_** traffic to be directed?")
  - `Target`: **_Where_** to direct the traffic?

    - `Local route`

- **_Subnet_ route table**
- **_Gateway_ route table**

- **_Main_ route table**
- **_Custom_ route table**

[^1.4.1]: <https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/how-elastic-load-balancing-works.html>
[^1.4.2]: <https://aws.amazon.com/blogs/aws/amazon-route-53-elb-integration-dns-failover/>
[^2.2.1]: <https://aws.amazon.com/blogs/database/improving-application-availability-with-amazon-rds-proxy/>
[^2.2.2]: <https://aws.amazon.com/blogs/database/improving-application-availability-with-amazon-rds-proxy/#:~:text=logic%20goes%20away.-,Amazon%20RDS%20Multi%2DAZ,-One%20of%20the>
[^3.8.1]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/storage-optimized-instances.html>
[^3.8.2]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/provisioned-iops.html>
[^4.6.1]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/s3-arn-format.html>
[^5.2.1]: <https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html#RouteTables>
