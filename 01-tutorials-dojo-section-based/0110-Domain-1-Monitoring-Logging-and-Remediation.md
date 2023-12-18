# Tutorial Dojo - SOA-C02 - Domain 1: Monitoring, Logging, and Remediation

YOUR TIME: 01:34:33
You have reached 23 of 30 point(s), (76.67%)

| No  |     | Q                                                                                         | A                                                                                                                          | Ref    |
| --- | --- | ----------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | ------ |
|     |     |                                                                                           |                                                                                                                            |        |
| 1   | ✅  | Cfn: Central config for AMI                                                               | **System Manager** _Parameter Store_                                                                                       |        |
| 2   | ✅  | EC2: NACL, SG. User cannot access. Which service to use for investigating?                | VPC Flow Logs                                                                                                              |        |
| 3   | ✅  |                                                                                           |                                                                                                                            |        |
| 4   | ✅  |                                                                                           |                                                                                                                            |        |
| 5   | ✅  |                                                                                           |                                                                                                                            |        |
| 6   | ✅  |                                                                                           |                                                                                                                            |        |
| 7   | ❌  | Send event notification for all system alerts to phones/emails. Which service?            | SNS                                                                                                                        |        |
| 8   | ✅  |                                                                                           |                                                                                                                            |        |
| 9   | ✅  |                                                                                           |                                                                                                                            |        |
| 10  | ✅  |                                                                                           |                                                                                                                            |        |
| 11  | ✅  |                                                                                           |                                                                                                                            |        |
| 12  | ❌  | CloudFront: Reports                                                                       | CloudFront supports 5 type of reports                                                                                      | [1.12] |
| 13  | ✅  |                                                                                           |                                                                                                                            |        |
| 14  | ✅  |                                                                                           |                                                                                                                            |        |
| 15  | ✅  |                                                                                           |                                                                                                                            |        |
| 16  | ✅  |                                                                                           |                                                                                                                            |        |
| 17  | ❌  | IAM Identity Center: How to give permissions to access AWS services?                      | 1. Config permissions set(s); 2. Assign permission set(s) to a IAM Identity user/group                                     | [1.17] |
| 18  | ✅  |                                                                                           |                                                                                                                            |        |
| 19  | ✅  |                                                                                           |                                                                                                                            |        |
| 20  | ✅  |                                                                                           |                                                                                                                            |        |
| 21  | ❌  | ASG: Scale-out. Newly launched instances are not included in the aggregated metrics. Why? | (For step scaling), newly launch instance has a warm-up time, before it's counted to aggregated EC2 instance metrics       | [1.21] |
| 22  | ❌  | ASG: Launch 3 instances: 2 in the same AZ. Not error in ASG scaling history. Why?         | ASG is configured to deploy to 2 AZs.                                                                                      |        |
| 23  | ✅  |                                                                                           |                                                                                                                            |        |
| 24  | ✅  |                                                                                           |                                                                                                                            |        |
| 25  | ✅  |                                                                                           |                                                                                                                            |        |
| 26  | ✅  |                                                                                           |                                                                                                                            |        |
| 27  | ✅  |                                                                                           |                                                                                                                            |        |
| 28  | ✅  |                                                                                           |                                                                                                                            |        |
| 29  | ❌  | KMS: Delete CMK. What happened?                                                           | When delete a KMS key, AWS KMS requires you to set a waiting period of 7 – 30 days. The default waiting period is 30 days. | [1.29] |
| 30  | ❌  | ALB: 4 EC2 instances, 1: 95%, 3: 10%. Why?                                                | When scaling up, there is potential for unequal distribution of load due to stickiness -> Manually re-balance the load     | [1.30] |

[1.17]: https://docs.aws.amazon.com/singlesignon/latest/userguide/manage-your-accounts.html?icmpid=docs_sso_console#assigning-account-access
[1.21]: https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html#as-step-scaling-warmup
[1.29]: https://docs.aws.amazon.com/kms/latest/developerguide/deleting-keys.html
[1.30]: https://docs.aws.amazon.com/elasticloadbalancing/latest/application/sticky-sessions.html

## 1.12 CloudFront reports

CloudFront supports 5 type of reports

- Cache statistics

  - Total requests
  - Percentage of viewer requests by result type
  - Bytes transferred to viewers
  - HTTP status codes
  - Percentage of GET requests that didn't finish downloading

- Popular objects

- Top referrers

- Usage

  - Data transferred:
    - By Protocol: _HTTP/HTTPs_
    - By Destination: From CloudFront to your _users/origin_
  - Number of requests (by protocol)

- Viewers

  - Devices
  - Browsers
  - Operating systems
  - Locations

[1.12]: https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/reports.html
