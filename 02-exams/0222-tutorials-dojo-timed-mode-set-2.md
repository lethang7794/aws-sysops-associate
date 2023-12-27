# Tutorial Dojo - SOA-C02 - Timed Mode Set 2

Test time: 00:57:07

Score: 51/65 (78.5%):

|          | Domain                                   | Score | Percent |
| -------- | ---------------------------------------- | ----- | ------- |
| Domain 1 | Monitoring, Logging, and Remediation     | 9/13  | 69.23%  |
| Domain 2 | Reliability and Business Continuity      | 7/9   | 77.78%  |
| Domain 3 | Deployment, Provisioning, and Automation | 10/12 | 83.33%  |
| Domain 4 | Security and Compliance                  | 7/10  | 70%     |
| Domain 5 | Networking and Content Delivery          | 9/9   | 100%    |
| Domain 6 | Cost and Performance Optimization        | 9/12  | 75%     |

## Domain 1: Monitoring, Logging, and Remediation

| No  |     | Q                                                                                                         | A                                                                                                                                                                                                     | Ref |
| --- | --- | --------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
|     |     |                                                                                                           |                                                                                                                                                                                                       |     |
| 1   | ❌  | Track & review usage of AWS resources: Cost of current month, last 3 months, forecast next 3 months.      | AWS `Cost Explorer` (with its **new** `Cost & Usage Report`)                                                                                                                                          |     |
| 2   | ✅  |                                                                                                           |                                                                                                                                                                                                       |     |
| 3   | ✅  |                                                                                                           |                                                                                                                                                                                                       |     |
| 4   | ✅  |                                                                                                           |                                                                                                                                                                                                       |     |
| 5   | ✅  |                                                                                                           |                                                                                                                                                                                                       |     |
| 6   | ✅  |                                                                                                           |                                                                                                                                                                                                       |     |
| 7   | ❌  | ELB: Capture information about activity                                                                   | 1. ELB Access Logs; 2. CloudWatch, 3. CloudTrail                                                                                                                                                      |     |
| 8   | ❌  | EC2, ELB, DynamoDB: A group of beta-testing users. Some can, some cannot access login page. Troubleshoot? | Create a VPC Flow Logs                                                                                                                                                                                |     |
| 9   | ✅  |                                                                                                           |                                                                                                                                                                                                       |     |
| 10  | ✅  |                                                                                                           |                                                                                                                                                                                                       |     |
| 11  | ❌  | Reports & statistics about EC2 instances in multiple regions. Viewing aggregation statistics in CW?       | CW supports cross-accounts cross-regions dashboard[^II.1.11.1]. Use CloudWatch **metric math**[^II.1.11.2] to aggregate and transform metrics from multiple accounts and Regions. Example[^II.1.11.3] |     |
| 12  | ✅  |                                                                                                           |                                                                                                                                                                                                       |     |
| 13  | ✅  |                                                                                                           |                                                                                                                                                                                                       |     |

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
| 8   | ✅  |     |     |     |
| 9   | ✅  |     |     |     |

## Domain 3: Deployment, Provisioning, and Automation

| No  |     | Q                                              | A                                                                                    | Ref |
| --- | --- | ---------------------------------------------- | ------------------------------------------------------------------------------------ | --- |
|     |     |                                                |                                                                                      |     |
| 1   | ❌  | Elasticache Memcached: Eviction too high.      | [Elasticache Scaling](#31-elasticache-scaling): Vertical/Horizontal? Online/Offline? |     |
| 2   | ✅  |                                                |                                                                                      |     |
| 3   | ✅  |                                                |                                                                                      |     |
| 4   | ✅  |                                                |                                                                                      |     |
| 5   | ❌  | Elasticache Memcached: Eviction is increasing. | [Elasticache Scaling](#31-elasticache-scaling)                                       |     |
| 6   | ✅  |                                                |                                                                                      |     |
| 7   | ✅  |                                                |                                                                                      |     |
| 8   | ✅  |                                                |                                                                                      |     |
| 9   | ✅  |                                                |                                                                                      |     |
| 10  | ✅  |                                                |                                                                                      |     |
| 11  | ✅  |                                                |                                                                                      |     |
| 12  | ✅  |                                                |                                                                                      |     |

## Domain 4: Security and Compliance

| No  |     | Q                                                                                                      | A                                                                                                                                                                                    | Ref                                                             |
| --- | --- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------- |
|     |     |                                                                                                        |                                                                                                                                                                                      |                                                                 |
| 1   | ✅  |                                                                                                        |                                                                                                                                                                                      |                                                                 |
| 2   | ✅  |                                                                                                        |                                                                                                                                                                                      |                                                                 |
| 3   | ✅  |                                                                                                        |                                                                                                                                                                                      |                                                                 |
| 4   | ❌  | IAM Policy: `s3:GetObject` action. Which resource ARN?                                                 | `s3:GetObject` only applies to S3 objects (`arn:aws:s3:::BUCKET_NAME/*`)                                                                                                             | S3 ARN[^II.4.4.1], S3 Bucket Policy - Specify Folder[^II.4.4.2] |
| 5   | ✅  |                                                                                                        |                                                                                                                                                                                      |                                                                 |
| 6   | ❌  | AWS Shared Responsibility Model                                                                        | AWS: Protect against packet sniffing (not secure communicate between ELB & EC2)                                                                                                      | [^II.4.6.1]                                                     |
| 7   | ❌  | Cfn: Prevent stack resources from being unintentionally updated or deleted during a stack update. How? | Use `StackPolicy`. Whitelist only updatable resources or blacklist protected resourcesBy default, anyone with stack update permissions can update all of the resources in the stack. | [^II.4.7.1]                                                     |
|     |     |                                                                                                        | (By default, anyone with stack update permissions can update all of the resources in the stack)                                                                                      |                                                                 |
| 8   | ✅  |                                                                                                        |                                                                                                                                                                                      |                                                                 |
| 9   | ✅  |                                                                                                        |                                                                                                                                                                                      |                                                                 |
| 10  | ✅  |                                                                                                        |                                                                                                                                                                                      |                                                                 |

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

| No  |     | Q                                                                     | A                                                                                                                                                                  | Ref                                                                        |
| --- | --- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------- |
|     |     |                                                                       |                                                                                                                                                                    |                                                                            |
| 1   | ❌  | ASG: Terminate an instance without reducing the ASG desired capacity? | `aws autoscaling terminate-instance-in-auto-scaling-group --instance-id INSTANCE_ID --no-should-decrement-desired-capacity`                                        | [^II.6.1.1]                                                                |
| 2   | ✅  |                                                                       |                                                                                                                                                                    |                                                                            |
| 3   | ✅  |                                                                       |                                                                                                                                                                    |                                                                            |
| 4   | ✅  |                                                                       |                                                                                                                                                                    |                                                                            |
| 5   | ✅  |                                                                       |                                                                                                                                                                    |                                                                            |
| 6   | ✅  |                                                                       |                                                                                                                                                                    |                                                                            |
| 7   | ❌  | Enforce tagging for IaC resources                                     | 1. Cfn Hooks; 2. `Service Catalog` **`TagOptions Library`**                                                                                                        | Enforcing tagging[^II.6.7.1] Service Catalog TagOptions Library[^II.6.7.2] |
| 8   | ❌  | S3: Upload 70TB to S3 Glacier. How?                                   | 1a. Upload to S3 IA (via S3 Console) -> Use Lifecycle rule to move to Glacier; 1b. Use Snowball instead of S3 Console; 2. Use API to upload directly to S3 Glacier |                                                                            |
| 9   | ✅  |                                                                       |                                                                                                                                                                    |                                                                            |
| 10  | ✅  |                                                                       |                                                                                                                                                                    |                                                                            |
| 11  | ✅  |                                                                       |                                                                                                                                                                    |                                                                            |
| 12  | ✅  |                                                                       |                                                                                                                                                                    |                                                                            |

## 3.1 Elasticache scaling

TODO

[^II.1.11.1]: <https://aws.amazon.com/about-aws/whats-new/2019/11/amazon-cloudwatch-launches-cross-account-cross-region-dashboards/>
[^II.1.11.2]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/using-metric-math.html>
[^II.1.11.3]: <https://aws.amazon.com/blogs/mt/using-amazon-cloudwatch-metrics-math-to-monitor-and-scale-resources/>
[^II.4.4.1]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/s3-arn-format.html>
[^II.4.4.2]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html#example-bucket-policies-folders>
[^II.4.6.1]: <https://aws.amazon.com/compliance/shared-responsibility-model/>
[^II.4.7.1]: <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/protect-stack-resources.html#stack-policy-reference>
[^II.6.1.1]: <https://awscli.amazonaws.com/v2/documentation/api/latest/reference/autoscaling/terminate-instance-in-auto-scaling-group.html>
[^II.6.7.1]: <https://docs.aws.amazon.com/whitepapers/latest/tagging-best-practices/implementing-and-enforcing-tagging.html>
[^II.6.7.2]: <https://docs.aws.amazon.com/servicecatalog/latest/adminguide/tagoptions.html>
