# Tutorial Dojo - SOA-C02 - Domain 6: Cost and Performance Optimization

| No  |     | Q                                                                                                               | A                                                                                                                                                                                                                                                                                          | Ref                 |
| --- | --- | --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------- |
|     |     |                                                                                                                 |                                                                                                                                                                                                                                                                                            |                     |
| 1   | ✅  | EC2: Optimize cost?                                                                                             | 1. Use `AWS Compute Optimizer`[^6.1.1][^6.1.2]; 2. Purchase `Saving Plans`[^6.1.3]                                                                                                                                                                                                         |                     |
| 2   | ❌  | Billing alert. How to turn on?                                                                                  | 1. `Billing & Cost Management`: `Billing reference`: `Alert preferences` 👈 It's `CloudWatch billing alerts`                                                                                                                                                                               | [^6.2.1] [^6.2.2]   |
| 3   | ✅  | S3: Analyze data with SQL syntax. How?                                                                          | Use Amazon `Athena`                                                                                                                                                                                                                                                                        | [^6.3]              |
| 4   | ✅  | File Gateway: Rarely access after 60 days, but should be available immediately. Cost-optimize?                  | `S3 Lifecycle` : Rule : `Transition` : 60 days -> `IA` storage class                                                                                                                                                                                                                       |                     |
| 5   | ✅  | EC2 fleet: Outdated OS: Mitigate vulnerability?                                                                 | AWS `Systems Manager` : `Patch Manager`[^6.5]                                                                                                                                                                                                                                              |                     |
| 6   | ✅  | EC2 fleet: Diversity instance family: Cost-optimize & minimize downtime?                                        | [Allocation strategies for Spot Instances](#66-allocation-strategies-for-spot-instances)                                                                                                                                                                                                   |                     |
| 7   | ✅  | S3: Static website hosting: Slow: Improve?                                                                      | Use `CloudFront`                                                                                                                                                                                                                                                                           |                     |
| 8   | ❌  | ASG: Scaling process: `Suspend-Resume`: Manually & administrative Suspension                                    | Type of scaling process: `Launch`, `Terminate`, `AddToLoadBalancer`, `AZRebalance`, ...                                                                                                                                                                                                    | [^6.8]              |
| 9   | ❌  | ECS: EBS-backed instance: after `pending` immediately `terminated`. Why?                                        | 1. Get the termination reason with console/CLI/CloudTrail; 2. Maybe: Exceed EBS volume limit, can't decrypt...                                                                                                                                                                             | [^6.9]              |
| 10  | ❌  | RDS: High read operations. Fix (cost-effective)?                                                                | 1. Read-replica; 2. Elasticache (Isn't this cost-effective)                                                                                                                                                                                                                                |                     |
| 11  | ❌  | Elasticache for Redis: Resize?                                                                                  | Elasticache for Redis supports _online_ vertical scaling (dynamically scale with minimal downtime).                                                                                                                                                                                        | [^6.11.1] [^6.11.2] |
| 12  | ✅  | On-premise: Backup: Available locally + block-based + POSIX. Which service?                                     | Storage Gateway : Volume Gateway (Stored-volume)                                                                                                                                                                                                                                           | [^6.12]             |
| 13  | ✅  | 2 VPCs - 2 regions + On-premise: Low-latency, high bandwidth connection. Cost-effective?                        | `Direct Connect` + Direct Connect **Gateway** 👈 1 DX connection share between many VPCs <- cost-effective                                                                                                                                                                                 |                     |
| 14  | ✅  | 3 VPCs - 3 accounts: Connect all together. Cost effective?                                                      | VPC peering + full mesh config                                                                                                                                                                                                                                                             |                     |
| 15  | ❌  | AWS Organization: Monthly cost per department. How?                                                             | 1. Standardize tags attached to AWS resources (using AWS Organization: Policies[^6.15.1] : **Tag Policies**[^6.15.2]); 2. Manage _compliance_ with tag polices (using AWS **Resource Groups**: Tag Editor console[^6.15.3] / Tagging API[^6.15.4]); 3. Tagging your AWS resources[^6.15.5] |                     |
| 16  | ✅  | Multiple AWS accounts: Centrally manage polices & billing. How?                                                 | Use AWS Organizations                                                                                                                                                                                                                                                                      |                     |
| 17  | ✅  | S3: Monitor & verify that the bucket not publicly accessible. How?                                              | Use `AWS Config` + Rule `s3-bucket-publice-read-prohibited`[^6.17]                                                                                                                                                                                                                         |                     |
| 18  | ✅  | ALB + EC2 Fleet: Reports all IP address access + API requests to AWS resources. Which service?                  | VPC `Flow Logs` (or ALB access logs (more detail)) + CloudTrail                                                                                                                                                                                                                            |                     |
| 19  | ✅  | ALB + ASG (On-demand EC2): Slow load: Improve - cost-effective?                                                 | `CloudFront`                                                                                                                                                                                                                                                                               |                     |
| 20  | ✅  | AWS Systems Manager features?                                                                                   | 1. Patch OS (Systems Manager); 2. Run automation workflow (AWS/custom); 3. Receive noti ...                                                                                                                                                                                                |                     |
| 21  | ✅  | ASG (Spot EC2). Slow load during office hours. Fix?                                                             | Add a `Scheduled scaling policy` [^6.21.1]. Example [^6.21.2]                                                                                                                                                                                                                              |                     |
| 22  | ✅  | EC2 + EBS (general-purpose). Increase IOPS?                                                                     | 1. Use Provisioned IOPS SSD volume [^6.22.1]; 2. Set up READ 0 [^6.22.2]                                                                                                                                                                                                                   |                     |
| 23  | ✅  | EC2 Fleet: Some instances have 0 CPU credit. Fix?                                                               | 1. Upgrade instance type [^6.23.1]; 2. (For t2, t3, t4 instances) Use `Unlimited` mode [^6.23.2]                                                                                                                                                                                           |                     |
| 24  | ❌  | Backup & Archiving system for on-premise. Immediately access within minutes in 6 month, available for 10 years. | 1. Use Storage Gateway: File Gateway TODO (Check) : Stored volume / ~~Cached volume~~; 2. Use life cycle police to archive data after 6 months                                                                                                                                             |                     |
| 25  | ✅  | On-premise: Migrate to AWS: HA + Protect against SQL-injection, XSS, HTTP flood attack?                         | `ALB` (not `NLB` <- cannot integrate with WAF) + `WAF` + `Shield`                                                                                                                                                                                                                          |                     |
| 26  | ✅  | RDS: Heavily used by data analytics app: Cannot handle high volume. Fix?                                        | 1. Upgrade RDS instance type; 2. Add Read Replica                                                                                                                                                                                                                                          |                     |
| 27  | ❌  | ASG: EC2: Workload goes up -> issue. Fix?                                                                       | Upgrade to a larger instance type                                                                                                                                                                                                                                                          |                     |
| 28  | ❌  | Employee work files: No longer access after 3 months: Reduce cost & keep the files?                             | `S3 Lifecycle` [^6.28.1]: `Transition` action [^6.28.2] / ~~Expiration action~~: To Glacier after 90 days                                                                                                                                                                                  |                     |
| 29  | ❌  | Ensure tags are consistently applied to resources created across all accounts?                                  | [Best practice for tagging AWS resources](#629-best-practice-for-tagging-aws-resources) [^6.29]                                                                                                                                                                                            |                     |

## 6.6 Allocation strategies for Spot Instances

- Allocation strategies:
  - `lowestPrice` (default) 🛑🛑🛑💰
    - Used with `InstancePoolsToUseCount`
  - `priceCapacityOptimized` (recommended) 🛑🛑💰💰
  - `capacityOptimized` 🛑💰💰💰
  - `diversified`: Request evenly across all available pools

## 6.11 Is there any other AWS services support online vertical scaling?

TODO: Research services supports online vertical scaling

## 6.29 Best practice for tagging AWS resources

### Enforcing tagging [^6.29.2]

- Manually managed resources

  - AWS Resource Group : Tag Editor console / Tagging API allows
  - EC2 launch template : Tags
  - AWS Config Rules: check for required_tags & start a Lambda function to apply them

- Infrastructure as code (IaC) managed resources

  - CloudFormation : Template : Resource Tags
    - AWS CloudFormation Hooks
  - AWS Service Catalog

- CI/CD pipeline managed resources
  - CloudFormation
    - AWS CloudFormation Guard

[^6.1.1]: <https://docs.aws.amazon.com/compute-optimizer/latest/ug/what-is-compute-optimizer.html>
[^6.1.2]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-recommendations.html>
[^6.1.3]: <https://docs.aws.amazon.com/savingsplans/latest/userguide/what-is-savings-plans.html>
[^6.2.1]: <https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-pref.html#alert-preferences>
[^6.2.2]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/monitor_estimated_charges_with_cloudwatch.html>
[^6.3]: <https://docs.aws.amazon.com/athena/latest/ug/what-is.html>
[^6.5]: <https://docs.aws.amazon.com/systems-manager/latest/userguide/patch-manager.html>
[^6.8]: <https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-suspend-resume-processes.html>
[^6.9]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/troubleshooting-launch.html#troubleshooting-launch-internal>
[^6.11.1]: <https://aws.amazon.com/about-aws/whats-new/2019/08/amazon-elasticache-announces-online-vertical-scaling-for-redis-cluster-mode/>
[^6.11.2]: <https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/redis-cluster-vertical-scaling.html>
[^6.12]: <https://docs.aws.amazon.com/directconnect/latest/UserGuide/direct-connect-gateways-intro.html>
[^6.15.1]: <https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies.html>
[^6.15.2]: <https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_tag-policies.html>
[^6.15.3]: <https://docs.aws.amazon.com/tag-editor/latest/userguide/tag-editor.html>
[^6.15.4]: <https://docs.aws.amazon.com/resourcegroupstagging/latest/APIReference/overview.html>
[^6.15.5]: <https://docs.aws.amazon.com/tag-editor/latest/userguide/tagging.html>
[^6.17]: <https://aws.amazon.com/blogs/security/how-to-use-aws-config-to-monitor-for-and-respond-to-amazon-s3-buckets-allowing-public-access/>
[^6.21.1]: <https://docs.aws.amazon.com/autoscaling/ec2/userguide/ec2-auto-scaling-scheduled-scaling.html>
[^6.21.2]: <https://media.tutorialsdojo.com/asg-scheduled-scaling-policy.png>
[^6.22.1]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html#vol-type-ssd>
[^6.23.1]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html>
[^6.22.2]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/raid-config.html#raid-config-options>
[^6.23.2]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/burstable-performance-instances-unlimited-mode.html>
[^6.28.1]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html>
[^6.28.2]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/lifecycle-transition-general-considerations.html>
[^6.29]: <https://docs.aws.amazon.com/whitepapers/latest/tagging-best-practices/tagging-best-practices.html>
[^6.29.2]: <https://docs.aws.amazon.com/whitepapers/latest/tagging-best-practices/implementing-and-enforcing-tagging.html>
