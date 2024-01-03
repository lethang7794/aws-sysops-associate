# Tutorial Dojo - SOA-C02 - Review Mode Set 2

Test time: 00:44:27

Score: 64/65 (98.46%):

|          | Domain                                   | Score | Percent |
| -------- | ---------------------------------------- | ----- | ------- |
| Domain 1 | Monitoring, Logging, and Remediation     | 13/13 | 100%    |
| Domain 2 | Reliability and Business Continuity      | 9/9   | 100%    |
| Domain 3 | Deployment, Provisioning, and Automation | 12/12 | 100%    |
| Domain 4 | Security and Compliance                  | 10/10 | 100%    |
| Domain 5 | Networking and Content Delivery          | 8/9   | 88.89%  |
| Domain 6 | Cost and Performance Optimization        | 12/12 | 100%    |

## Domain 1: Monitoring, Logging, and Remediation

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   | ✅  |     |     |     |
| 2   | ✅  |     |     |     |
| 3   | ✅  |     |     |     |
| 4   | ✅  |     |     |     |
| 5   | ✅  |     |     |     |
| 6   | ✅  |     |     |     |
| 7   | ✅  |     |     |     |
| 8   | ✅  |     |     |     |
| 9   | ✅  |     |     |     |
| 10  | ✅  |     |     |     |
| 11  | ✅  |     |     |     |
| 12  | ✅  |     |     |     |
| 13  | ✅  |     |     |     |

## Domain 2: Reliability and Business Continuity

| No  |     | Q                                | A                                                                                                                                                              | Ref      |
| --- | --- | -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
|     |     |                                  |                                                                                                                                                                |          |
| 1   | ✅  |                                  |                                                                                                                                                                |          |
| 2   | ✅  |                                  |                                                                                                                                                                |          |
| 3   | ✅  |                                  |                                                                                                                                                                |          |
| 4   | ❌  | RDS: Take snapshot: Performance? | 1. For Single-AZ DB instance, creating DB snapshot results in a brief I/O suspension that can last from a few seconds to a few minutes                         | [^2.4.1] |
|     |     |                                  | 2. With Multi-AZ deployment, I/O activity is not suspended on your primary during backup, because the backup is taken from the standby (except for SQL Server) |          |
|     |     |                                  | 3. Taking snapshot on a replica will not effect I/O activity, but the data may be lag behind master instance                                                   | [^2.4.2] |
| 5   | ✅  |                                  |                                                                                                                                                                |          |
| 6   | ✅  |                                  |                                                                                                                                                                |          |
| 7   | ✅  |                                  |                                                                                                                                                                |          |
| 8   | ✅  |                                  |                                                                                                                                                                |          |
| 9   | ✅  |                                  |                                                                                                                                                                |          |

## Domain 3: Deployment, Provisioning, and Automation

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   | ✅  |     |     |     |
| 2   | ✅  |     |     |     |
| 3   | ✅  |     |     |     |
| 4   | ✅  |     |     |     |
| 5   | ✅  |     |     |     |
| 6   | ✅  |     |     |     |
| 7   | ✅  |     |     |     |
| 8   | ✅  |     |     |     |
| 9   | ✅  |     |     |     |
| 10  | ✅  |     |     |     |
| 11  | ✅  |     |     |     |
| 12  | ✅  |     |     |     |

## Domain 4: Security and Compliance

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   | ✅  |     |     |     |
| 2   | ✅  |     |     |     |
| 3   | ✅  |     |     |     |
| 4   | ✅  |     |     |     |
| 5   | ✅  |     |     |     |
| 6   | ✅  |     |     |     |
| 7   | ✅  |     |     |     |
| 8   | ✅  |     |     |     |
| 9   | ✅  |     |     |     |
| 10  | ✅  |     |     |     |

## Domain 5: Networking and Content Delivery

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   | ✅  |     |     |     |
| 2   | ✅  |     |     |     |
| 3   | ✅  |     |     |     |
| 4   | ✅  |     |     |     |
| 5   | ✅  |     |     |     |
| 6   | ✅  |     |     |     |
| 7   | ✅  |     |     |     |
| 8   | ✅  |     |     |     |
| 9   | ✅  |     |     |     |

## Domain 6: Cost and Performance Optimization

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   | ✅  |     |     |     |
| 2   | ✅  |     |     |     |
| 3   | ✅  |     |     |     |
| 4   | ✅  |     |     |     |
| 5   | ✅  |     |     |     |
| 6   | ✅  |     |     |     |
| 7   | ✅  |     |     |     |
| 8   | ✅  |     |     |     |
| 9   | ✅  |     |     |     |
| 10  | ✅  |     |     |     |
| 11  | ✅  |     |     |     |
| 12  | ✅  |     |     |     |

[^2.4.1]: <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateSnapshot.html>
[^2.4.2]: <https://aws.amazon.com/about-aws/whats-new/2013/08/28/amazon-rds-read-replica-new-features/>
