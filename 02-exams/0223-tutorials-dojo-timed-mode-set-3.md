# Tutorial Dojo - SOA-C02 - Timed Mode Set 3

Test time: 00:53:45

Score: 59/65 (90.8%):

|          | Domain                                   | Score | Percent |
| -------- | ---------------------------------------- | ----- | ------- |
| Domain 1 | Monitoring, Logging, and Remediation     | 10/12 | 83.33%  |
| Domain 2 | Reliability and Business Continuity      | 7/7   | 100%    |
| Domain 3 | Deployment, Provisioning, and Automation | 9/10  | 90%     |
| Domain 4 | Security and Compliance                  | 16/16 | 100%    |
| Domain 5 | Networking and Content Delivery          | 9/10  | 90%     |
| Domain 6 | Cost and Performance Optimization        | 8/10  | 80%     |

## Domain 1: Monitoring, Logging, and Remediation

| No  |     | Q                                                                                                  | A                                                                                                                                                                                          | Ref                                                                                                              |
| --- | --- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
|     |     |                                                                                                    |                                                                                                                                                                                            |                                                                                                                  |
| 1   | ✅  |                                                                                                    |                                                                                                                                                                                            |                                                                                                                  |
| 2   | ✅  |                                                                                                    |                                                                                                                                                                                            |                                                                                                                  |
| 3   | ✅  |                                                                                                    |                                                                                                                                                                                            |                                                                                                                  |
| 4   | ✅  |                                                                                                    |                                                                                                                                                                                            |                                                                                                                  |
| 5   | ✅  |                                                                                                    |                                                                                                                                                                                            |                                                                                                                  |
| 6   | ❌  | Aggregate CPUUtilization across EC2 instances in multi VPCS in multi regions                       | - Metrics are completely separate between Regions, but you can use **metric math** to aggregate similar metrics across Regions[^1.6.1]                                                     | Aggregate statistic across resources[^1.6.1]; Metric math[^1.6.2]; Cross-account cross-Region dashboards[^1.6.3] |
|     |     |                                                                                                    | - e.g. you can aggregate statistics for your EC2 instances that have _detailed monitoring_ enabled[^1.6.1]                                                                                 |                                                                                                                  |
| 7   | ✅  |                                                                                                    |                                                                                                                                                                                            |                                                                                                                  |
| 8   | ✅  |                                                                                                    |                                                                                                                                                                                            |                                                                                                                  |
| 9   | ✅  |                                                                                                    |                                                                                                                                                                                            |                                                                                                                  |
| 10  | ❌  | AWS Organization, AWS Directory Service, AWS IAM Identity Center: Where to config permission sets? | - **IAM Identity Center** : Multi-accounts permission : **AWS Accounts\***/**Permission Sets** (These AWS accounts are given to IAM Identity Center user/group (for multi-account access)) |                                                                                                                  |
|     |     |                                                                                                    | - **AWS Organizations** : **AWS Accounts\*\*** (Invitations) / **Policies** (SCP, Tag Policies) (These AWS accounts are organized to Organization Unit - OU)                               |                                                                                                                  |
| 11  | ✅  |                                                                                                    |                                                                                                                                                                                            |                                                                                                                  |
| 12  | ✅  |                                                                                                    |                                                                                                                                                                                            |                                                                                                                  |

## Domain 2: Reliability and Business Continuity

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

## Domain 3: Deployment, Provisioning, and Automation

| No  |     | Q                                               | A                                                                                                                                        | Ref |
| --- | --- | ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | --- |
|     |     |                                                 |                                                                                                                                          |     |
| 1   | ✅  |                                                 |                                                                                                                                          |     |
| 2   | ✅  |                                                 |                                                                                                                                          |     |
| 3   | ✅  |                                                 |                                                                                                                                          |     |
| 4   | ✅  |                                                 |                                                                                                                                          |     |
| 5   | ✅  |                                                 |                                                                                                                                          |     |
| 6   | ✅  |                                                 |                                                                                                                                          |     |
| 7   | ✅  |                                                 |                                                                                                                                          |     |
| 8   | ❌  | Storage Gateway: `CachePercentUsed` > 80%. Fix? | - Volume Gateway (cached volume) has a on-premise/EC2 VM (`cache storage` & `upload buffer`)[^3.8.1]                                     |     |
|     |     |                                                 | - To add `cache storage`/`upload buffer` to existing gateway, create a new disk (don't extend the size of existing disk)[^3.8.2][^3.8.3] |     |
| 9   | ✅  |                                                 |                                                                                                                                          |     |
| 10  | ✅  |                                                 |                                                                                                                                          |     |

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
| 11  | ✅  |     |     |     |
| 12  | ✅  |     |     |     |
| 13  | ✅  |     |     |     |
| 14  | ✅  |     |     |     |
| 15  | ✅  |     |     |     |
| 16  | ✅  |     |     |     |

## Domain 5: Networking and Content Delivery

| No  |     | Q                                                                                                                 | A                                         | Ref |
| --- | --- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------- | --- |
|     |     |                                                                                                                   |                                           |     |
| 1   | ✅  |                                                                                                                   |                                           |     |
| 2   | ✅  |                                                                                                                   |                                           |     |
| 3   | ✅  |                                                                                                                   |                                           |     |
| 4   | ✅  |                                                                                                                   |                                           |     |
| 5   | ✅  |                                                                                                                   |                                           |     |
| 6   | ✅  |                                                                                                                   |                                           |     |
| 7   | ✅  |                                                                                                                   |                                           |     |
| 8   | ✅  |                                                                                                                   |                                           |     |
| 9   | ❌  | On-premise servers: Route 53 Fail-over + Route traffic to primary instance if health check returns 2xx, 3xx. How? | Use 2 Route 53 A record + HTTP healtcheck |     |
| 10  | ✅  |                                                                                                                   |                                           |     |

## Domain 6: Cost and Performance Optimization

| No  |     | Q                                                                                            | A                                                                                                                      | Ref      |
| --- | --- | -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | -------- |
|     |     |                                                                                              |                                                                                                                        |          |
| 1   | ✅  |                                                                                              |                                                                                                                        |          |
| 2   | ✅  |                                                                                              |                                                                                                                        |          |
| 3   | ✅  |                                                                                              |                                                                                                                        |          |
| 4   | ❌  | EC2: Automate start/stop instances for different environments during non-business time. How? | **Tagging** resources[^6.4.1] + `Systems Manager` **`Automation`**[^6.4.2]                                             |          |
| 5   | ✅  |                                                                                              |                                                                                                                        |          |
| 6   | ✅  |                                                                                              |                                                                                                                        |          |
| 7   | ❌  | EC2: EBS-backed instances always go from `pending` to `terminated` immediately. Why?         | 1. Exceed EBS volume limits[^6.7.1] (the number of volume attach to an instance)                                       |          |
|     |     |                                                                                              | 2. Instance store-backed AMI missing a required part; 3. Snapshot corrupt; 4. Cannot decrypt encrypted snapshot/volume | [^6.7.2] |
| 8   | ✅  |                                                                                              |                                                                                                                        |          |
| 9   | ✅  |                                                                                              |                                                                                                                        |          |
| 10  | ✅  |                                                                                              |                                                                                                                        |          |

[^1.6.1]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/GetSingleMetricAllDimensions.html>
[^1.6.2]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/using-metric-math.html>
[^1.6.3]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_xaxr_dashboard.html>
[^3.8.1]: <https://docs.aws.amazon.com/storagegateway/latest/vgw/StorageGatewayConcepts.html#storage-gateway-cached-concepts>
[^3.8.2]: <https://docs.aws.amazon.com/storagegateway/latest/vgw/ManagingLocalStorage-common.html#ConfiguringLocalDiskStorage>
[^3.8.3]: <https://docs.aws.amazon.com/storagegateway/latest/vgw/WhatIsStorageGateway.html#planning-gateway-deployment>
[^6.4.1]: <https://docs.aws.amazon.com/systems-manager/latest/userguide/tagging-resources.html>
[^6.4.2]: <https://docs.aws.amazon.com/systems-manager/latest/userguide/tagging-automations.html>
[^6.7.1]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/volume_limits.html>
[^6.7.2]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/troubleshooting-launch.html#troubleshooting-launch-internal>
