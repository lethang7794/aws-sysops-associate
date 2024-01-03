# Tutorial Dojo - SOA-C02 - Review Mode Set 5

Test time: 00:36:49

Score: 61/65 (93.65%):

|          | Domain                                   | Score | Percent |
| -------- | ---------------------------------------- | ----- | ------- |
| Domain 1 | Monitoring, Logging, and Remediation     | 10/10 | 100%    |
| Domain 2 | Reliability and Business Continuity      | 5/6   | 83.33%  |
| Domain 3 | Deployment, Provisioning, and Automation | 15/16 | 93.75%  |
| Domain 4 | Security and Compliance                  | 15/16 | 93.75%  |
| Domain 5 | Networking and Content Delivery          | 9/9   | 100%    |
| Domain 6 | Cost and Performance Optimization        | 7/8   | 87.5%   |

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

## Domain 2: Reliability and Business Continuity

| No  |     | Q                                                                                     | A                   | Ref |
| --- | --- | ------------------------------------------------------------------------------------- | ------------------- | --- |
|     |     |                                                                                       |                     |     |
| 1   | ✅  |                                                                                       |                     |     |
| 2   | ❌  | EC2: High throughput storage + parallel shared access between servers. Which service? | EFS (not ~~`EBS`~~) |     |
| 3   | ✅  |                                                                                       |                     |     |
| 4   | ✅  |                                                                                       |                     |     |
| 5   | ✅  |                                                                                       |                     |     |
| 6   | ✅  |                                                                                       |                     |     |

## Domain 3: Deployment, Provisioning, and Automation

| No  |     | Q                                                        | A                                                            | Ref       |
| --- | --- | -------------------------------------------------------- | ------------------------------------------------------------ | --------- |
|     |     |                                                          |                                                              |           |
| 1   | ✅  |                                                          |                                                              |           |
| 2   | ✅  |                                                          |                                                              |           |
| 3   | ✅  |                                                          |                                                              |           |
| 4   | ✅  |                                                          |                                                              |           |
| 5   | ✅  |                                                          |                                                              |           |
| 6   | ✅  |                                                          |                                                              |           |
| 7   | ✅  |                                                          |                                                              |           |
| 8   | ✅  |                                                          |                                                              |           |
| 9   | ✅  |                                                          |                                                              |           |
| 10  | ✅  |                                                          |                                                              |           |
| 11  | ✅  |                                                          |                                                              |           |
| 12  | ✅  |                                                          |                                                              |           |
| 13  | ✅  |                                                          |                                                              |           |
| 14  | ❌  | Cfn: Stack with VPC, EC2: Deploy new stack: Failed. Why? | VPCs **`quota`** (a.k.a `limit`): 5 VPCs/region (soft quota) | [^3.14.1] |
| 15  | ✅  |                                                          |                                                              |           |
| 16  | ✅  |                                                          |                                                              |           |

## Domain 4: Security and Compliance

| No  |     | Q                                        | A                    | Ref                |
| --- | --- | ---------------------------------------- | -------------------- | ------------------ |
|     |     |                                          |                      |                    |
| 1   | ✅  |                                          |                      |                    |
| 2   | ✅  |                                          |                      |                    |
| 3   | ❌  | NLB + EC2: Deep package inspection. How? | AWS Network Firewall | What's new[^4.3.1] |
| 4   | ✅  |                                          |                      |                    |
| 5   | ✅  |                                          |                      |                    |
| 6   | ✅  |                                          |                      |                    |
| 7   | ✅  |                                          |                      |                    |
| 8   | ✅  |                                          |                      |                    |
| 9   | ✅  |                                          |                      |                    |
| 10  | ✅  |                                          |                      |                    |
| 11  | ✅  |                                          |                      |                    |
| 12  | ✅  |                                          |                      |                    |
| 13  | ✅  |                                          |                      |                    |
| 14  | ✅  |                                          |                      |                    |
| 15  | ✅  |                                          |                      |                    |
| 16  | ✅  |                                          |                      |                    |

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

| No  |      | Q                                                            | A                                                                      | Ref |
| --- | ---- | ------------------------------------------------------------ | ---------------------------------------------------------------------- | --- |
|     |      |                                                              |                                                                        |     |
| 1   | ✅   |                                                              |                                                                        |     |
| 2   | ✅   |                                                              |                                                                        |     |
| 3   | ❌❌ | Elasticache for Memcached: Vertical Scaling? Online/Offline? | Elasticache for Memcached only supports offline for horizontal scaling |     |
| 4   | ✅   |                                                              |                                                                        |     |
| 5   | ✅   |                                                              |                                                                        |     |
| 6   | ✅   |                                                              |                                                                        |     |
| 7   | ✅   |                                                              |                                                                        |     |
| 8   | ✅   |                                                              |                                                                        |     |

[^3.14.1]: <https://docs.aws.amazon.com/vpc/latest/userguide/amazon-vpc-limits.html>
[^4.3.1]: <https://aws.amazon.com/about-aws/whats-new/2020/11/introducing-aws-network-firewall/>
