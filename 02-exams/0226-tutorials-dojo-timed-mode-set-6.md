# Tutorial Dojo - SOA-C02 - Timed Mode Set 6

Test time: 00:33:46

Score: 19/36 (xx%):

|          | Domain                                   | Score | Percent |
| -------- | ---------------------------------------- | ----- | ------- |
| Domain 1 | Monitoring, Logging, and Remediation     | 3/6   | 50%     |
| Domain 2 | Reliability and Business Continuity      | 1/2   | 50%     |
| Domain 3 | Deployment, Provisioning, and Automation | 4/12  | 33.33%  |
| Domain 4 | Security and Compliance                  | 5/7   | 71.43%  |
| Domain 5 | Networking and Content Delivery          | 1/1   | 100%    |
| Domain 6 | Cost and Performance Optimization        | 5/8   | 62.5%   |

## Domain 1: Monitoring, Logging, and Remediation

| No  |     | Q                                                     | A                                                                                                                              | Ref               |
| --- | --- | ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
|     |     |                                                       |                                                                                                                                |                   |
| 1   | ❌  | EC2 + EBS: Monitor disk read/write? Which CW metrics? | EC2: `DiskReadBytes`/`DiskWriteBytes`                                                                                          | [^1.1.1] [^1.1.2] |
|     |     |                                                       | EBS: `VolumeReadBytes`/`VolumeWriteBytes`                                                                                      |                   |
|     |     |                                                       | EBS for Nitro-based instances: `EBSReadBytes`                                                                                  | [^1.1.3]          |
| 2   | ✅  |                                                       |                                                                                                                                |                   |
| 3   | ❌  | VPC Flow Logs: Change log format?                     | After you create a flow log, you cannot change its configuration or the flow log record format.                                | [^1.3.1]          |
|     |     |                                                       | 👉 Create a new flow logs with new `custom format`                                                                             | [^1.3.2]          |
| 4   | ✅  |                                                       |                                                                                                                                |                   |
| 5   | ✅  |                                                       |                                                                                                                                |                   |
| 6   | ❌  | ASG: CW dashboard to monitor EC2 instance of ASG?     | ASG auto automatically adds a tag to instances with a key of `aws:autoscaling:groupName`                                       |                   |
|     |     |                                                       | 👉 Create a CloudWatch `dashboard`[^1.6.1] & use CloudWatch `Metrics Explorer`[^1.6.2] to filter/visualize the metrics by tags |                   |

## Domain 2: Reliability and Business Continuity

| No  |     | Q             | A                              | Ref |
| --- | --- | ------------- | ------------------------------ | --- |
|     |     |               |                                |     |
| 1   | ❌  | EKS: Scaling? | [EKS Scaling](#21-eks-scaling) |     |
| 2   | ✅  |               |                                |     |

## Domain 3: Deployment, Provisioning, and Automation

| No  |     | Q                                                                                                                                 | A                                                                                                                                                                    | Ref |
| --- | --- | --------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
|     |     |                                                                                                                                   |                                                                                                                                                                      |     |
| 1   | ✅  |                                                                                                                                   |                                                                                                                                                                      |     |
| 2   | ❌  | Cfn StackSets: stack operation failed, stack instance status is `OUTDATED`. Why?                                                  | [Troubleshooting AWS CloudFormation StackSets](#32-troubleshooting-aws-cloudformation-stacksets)                                                                     |     |
| 3   | ✅  |                                                                                                                                   |                                                                                                                                                                      |     |
| 4   | ❌  | Cfn: Already built a prototype built a CloudWatch dashboard. How to re-create to with Cfn?                                        | Use `GetDashboard` API's data returned within `DashboardBody`                                                                                                        |     |
|     |     |                                                                                                                                   | - as the template for the new dashboard when you call `PutDashboard`[^3.4.1] API                                                                                     |     |
|     |     |                                                                                                                                   | - populate Cfn `AWS::CloudWatch::Dashboard`[^3.4.2] resource `DashboardBody` property                                                                                |     |
| 5   | ❌  | Package & publish software to AWS Systems Manager managed nodes. How?                                                             | [AWS Systems Manager Distributor](#35-aws-systems-manager-distributor)                                                                                               |     |
|     |     |                                                                                                                                   |                                                                                                                                                                      |     |
|     |     |                                                                                                                                   |                                                                                                                                                                      |     |
| 6   | ❌  | AWS Systems Manager Patch Manager: auto-approve 3-day patch for staging environment, 7-day patch for production environment. How? | 1. Assign distinct tags to staging and production servers                                                                                                            |     |
|     |     |                                                                                                                                   | 2. Create                                                                                                                                                            |     |
|     |     |                                                                                                                                   | - 2 patch baseline:[^3.6.1][^3.6.2] to include rules for auto-approving patches within days of their release                                                         |     |
|     |     |                                                                                                                                   | - 2 patch groups:[^3.6.3] to associate managed nodes with a specific patch baseline (using tags)                                                                     |     |
| 7   | ❌  | EC2: Windows instance, EFS. Cannot mount EFS volume. Fix?                                                                         | `EFS` is not supported on Windows instances[^3.7.1]. Instead use `FSx for Windows File Server`[^3.7.2][^3.7.3]                                                       |     |
| 8   | ✅  |                                                                                                                                   |                                                                                                                                                                      |     |
| 9   | ✅  |                                                                                                                                   |                                                                                                                                                                      |     |
| 10  | ❌  | CloudWatch Agent: Instances in multi-regions. How to share configuration & install CW Agent?                                      | 1. CW configuration can be stored as `Systems Manager` **`Parameter Store`** or as file (& stored in S3)[^3.10.1]                                                    |     |
|     |     |                                                                                                                                   | 2. To install CW Agent on EC2 instance[^3.10.2]                                                                                                                      |     |
|     |     |                                                                                                                                   | - Manually install the CW Agent                                                                                                                                      |     |
|     |     |                                                                                                                                   | - Automatically install using `Systems Manager` **`Run Command`**[^3.10.3][^3.10.4] (using the `AWS-ConfigureAWSPackage` document & `AmazonCloudWatchAgent` package) |     |
| 11  | ❌  | S3: Incomplete multipart upload. How to cleanup?                                                                                  | Use S3 bucket lifecycle `Delete incomplete multipart uploads` action (Web Console) (CLI `AbortIncompleteMultipartUpload` action[^3.11.2])                            |     |
| 12  | ❌  | Tape Gateway: `Not Enough Space` error. Fix?                                                                                      | Use `Automatic Tape Creation`[^3.12.1], Tape Gateway automatically creates new virtual tapes to maintain the minimum number of available tapes that you configure.   |     |

## Domain 4: Security and Compliance

| No  |     | Q                                                    | A                                                                                                                                                      | Ref |
| --- | --- | ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | --- |
|     |     |                                                      |                                                                                                                                                        |     |
| 1   | ✅  |                                                      |                                                                                                                                                        |     |
| 2   | ✅  |                                                      |                                                                                                                                                        |     |
| 3   | ❌  | AWS Client VPN: Reduce data transfer cost?           | By default, when you have a Client VPN[^4.3.1] endpoint, all traffic from clients is routed over the Client VPN tunnel                                 |     |
|     |     |                                                      | With `split-tunnel`[^4.3.2], the routes on the Client VPN endpoint route table are pushed to the device that is connected (to the Client VPN endpoint) |     |
| 4   |     |                                                      | 👉 Only traffic with a destination to the network matching a route from the Client VPN endpoint route table is routed over the Client VPN tunnel.      |     |
| 4   | ✅  |                                                      |                                                                                                                                                        |     |
| 5   | ❌  | IAM: Cross account permission between account A & B? | [Cross account resource access in IAM](#45-cross-account-resource-access-in-iam)                                                                       |     |
| 6   | ✅  |                                                      |                                                                                                                                                        |     |
| 7   | ✅  |                                                      |                                                                                                                                                        |     |

## Domain 5: Networking and Content Delivery

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   | ✅  |     |     |     |

## Domain 6: Cost and Performance Optimization

| No  |     | Q                                                                  | A                                                                                                                                                     | Ref |
| --- | --- | ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
|     |     |                                                                    |                                                                                                                                                       |     |
| 1   | ✅  |                                                                    |                                                                                                                                                       |     |
| 2   | ✅  |                                                                    |                                                                                                                                                       |     |
| 3   | ✅  |                                                                    |                                                                                                                                                       |     |
| 4   | ✅  |                                                                    |                                                                                                                                                       |     |
| 5   | ❌  | Notify when data transfer cost approach 70% threshold. How?        | Use `AWS Budgets`: **`Cost budget`**[^6.5.1]/`Usage budget`[^6.5.2] : Budget Detail (Amount: $; Scope: Services/Dimension) : Alert threshold          |     |
| 6   | ✅  |                                                                    |                                                                                                                                                       |     |
| 7   | ❌  | CloudFront: Reduce requests to origin?                             | Enable `Origin Shield`[^6.7.1][^6.7.2] (additional cache layer that help reduce load on origin). Examples: Global viewers[^6.7.3]; Multi CDNs[^6.7.4] |     |
| 8   | ❌  | EB2 + EBS: Create recommendation for EBS based on IOPS/throughput? | Use `AWS Compute Optimizer`[^6.8.0] (It can optimize: EC2, Lambda, ASG (EC2), ECS (Fargate),... & **EBS**[^6.8.1][^6.8.2] too)                        |     |

## 2.1 EKS Scaling

EKS supports two **autoscaling** products (cluster-level)

- K8s `Cluster Autoscaler`: adjusts the number of nodes in your cluster (use Auto Scaling Group).
- `Karpenter`: provision just-in-time compute resources that precisely meet the requirements of your workload.

Your workloads are deployed in containers, which are deployed in Pods in Kubernetes.

Once you've deployed multiple Pods that provide the same service, you can

- Vertically scale Pods up or down with the K8s `Vertical Pod Autoscaler`.
- Horizontally scale the number of Pods needed to meet demand up or down with the K8s `Horizontal Pod Autoscaler`.

## 3.2 Troubleshooting AWS CloudFormation StackSets

Common reasons for stack operation failure[^3.2.1]

- Target Account - Administrator Account - Permission
- Cfn Template
- Limit

## 3.5 AWS Systems Manager Distributor

### What is Distributor

`Distributor`[^3.5.1] helps you package and publish software to AWS Systems Manager managed nodes.

### How Distributor works?

When you create a package in Distributor, the system creates an AWS Systems Manager document (SSM document). You can attach .zip files to this document.

When you run Distributor, the system processes the instructions in the SSM document and installs the software package in the .zip file on the specified targets.

You can use

- SSM **`Run Command`** 👉 once-time
- SSM **`State Manager`** 👉 on a automated schedule

to control which of your managed nodes get a package and which version of that package.

## 4.5 Cross account resource access in IAM

With IAM, you can share access to AWS resources in a account to another accounts.[^4.5.1]

You can do this:

- Directly by using IAM resource-based policy[^4.5.2] (only supports S3, SNS, SQS)

  > [!NOTE]
  > When an account accesses a resource through another account using a resource-based policy:
  >
  > - The `principal`[^4.5.3] still works in the `trusted account` and does not have to give up their permissions to receive the role permissions
  > - In other words, the principal continues to have access to resources in the trusted account while having access to the resource in the `trusting account`

- In-directly via an IAM role[^4.5.4] as a proxy

  - Create a role in one AWS account that delegates specific permissions to another AWS account.

  - Use `cross-account IAM roles` that allows IAM principals in another AWS account to assume the role. [^4.5.5][^4.5.6]

  > [!NOTE]
  > A `cross-account IAM role` is an IAM role that includes a `trust policy`[^4.5.7] that allows IAM principals in another AWS account to assume the role.

  > [!NOTE]
  > When a principal switches to a role to temporarily use the permissions of the role, they give up their original permissions and take on the permissions assigned to the role they’ve assumed.

[^1.1.1]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html#ec2-cloudwatch-metrics>
[^1.1.2]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using_cloudwatch_ebs.html#ebs-volume-metrics>
[^1.1.3]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html#ebs-metrics-nitro>
[^1.3.1]: <https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html#flow-logs-limitations>
[^1.3.2]: <https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs-cwl.html#flow-logs-cwl-create-flow-log>
[^1.6.1]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Dashboards.html>
[^1.6.2]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch-Metrics-Explorer.html>
[^3.2.1]: <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-troubleshooting.html#common-reasons-for-stack-operation-failure>
[^3.4.1]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/APIReference/API_PutDashboard.html>
[^3.4.2]: <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-cloudwatch-dashboard.html>
[^3.5.1]: <https://docs.aws.amazon.com/systems-manager/latest/userguide/distributor.html>
[^3.6.1]: <https://docs.aws.amazon.com/systems-manager/latest/userguide/patch-manager.html>
[^3.6.2]: <https://docs.aws.amazon.com/systems-manager/latest/userguide/patch-manager-predefined-and-custom-patch-baselines.html>
[^3.6.3]: <https://docs.aws.amazon.com/systems-manager/latest/userguide/patch-manager-patch-groups.html>
[^3.7.1]: <https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/AmazonEFS.html>
[^3.7.2]: <https://docs.aws.amazon.com/fsx/latest/WindowsGuide/what-is.html>
[^3.7.3]: <https://docs.aws.amazon.com/AmazonECS/latest/developerguide/wfsx-volumes.html>
[^3.10.1]: <https://docs.aws.amazon.com/prescriptive-guidance/latest/implementing-logging-monitoring-cloudwatch/create-store-cloudwatch-configurations.html>
[^3.10.2]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent-on-EC2-Instance-fleet.html#download-CloudWatch-Agent-on-EC2-Instance-fleet>
[^3.10.3]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent-on-EC2-Instance-fleet.html#download-CloudWatch-Agent-on-EC2-Instance-SSM-fleet>
[^3.10.4]: <https://docs.aws.amazon.com/systems-manager/latest/userguide/distributor-working-with-packages-deploy.html#distributor-deploy-pkg-console>
[^3.11.2]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/mpu-abort-incomplete-mpu-lifecycle-config.html>
[^3.12.1]: <https://docs.aws.amazon.com/storagegateway/latest/tgw/managing-automatic-tape-creation.html>
[^4.3.1]: <https://docs.aws.amazon.com/vpn/latest/clientvpn-admin/what-is.html>
[^4.3.2]: <https://docs.aws.amazon.com/vpn/latest/clientvpn-admin/split-tunnel-vpn.html>
[^4.5.1]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies-cross-account-resource-access.html>
[^4.5.2]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies-cross-account-resource-access.html#access_policies-cross-account-using-resource-based-policies>
[^4.5.3]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html>
[^4.5.4]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies-cross-account-resource-access.html#access_policies-cross-account-using-roles>
[^4.5.5]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_aws-accounts.html#id_roles_common-scenarios_aws-accounts-example>
[^4.5.6]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html>
[^4.5.7]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html#term_trust-policy>
[^6.5.1]: <https://docs.aws.amazon.com/cost-management/latest/userguide/create-cost-budget.html>
[^6.5.2]: <https://docs.aws.amazon.com/cost-management/latest/userguide/create-usage-budget.html>
[^6.7.1]: <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/origin-shield.html>
[^6.7.2]: <https://aws.amazon.com/blogs/networking-and-content-delivery/using-cloudfront-origin-shield-to-protect-your-origin-in-a-multi-cdn-deployment/>
[^6.7.3]: <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/origin-shield.html#os-use-cases-global-viewers>
[^6.7.4]: <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/origin-shield.html#os-use-cases-multi-cdn>
[^6.8.0]: <https://docs.aws.amazon.com/compute-optimizer/latest/ug/what-is-compute-optimizer.html>
[^6.8.1]: <https://docs.aws.amazon.com/compute-optimizer/latest/ug/viewing-dashboard.html#dashboard-classifications-ebs>
[^6.8.2]: <https://docs.aws.amazon.com/compute-optimizer/latest/ug/savings-estimation-mode.html>
