# Tutorial Dojo - SOA-C02 - Review Mode Set 1

Test time: 00:30:03

Score: 61/65 (93%):

|          | Domain                                   | Score | Percent |
| -------- | ---------------------------------------- | ----- | ------- |
| Domain 1 | Monitoring, Logging, and Remediation     | 13/14 | 92.86%  |
| Domain 2 | Reliability and Business Continuity      | 10/10 | 100%    |
| Domain 3 | Deployment, Provisioning, and Automation | 12/13 | 92.31%  |
| Domain 4 | Security and Compliance                  | 11/11 | 100%    |
| Domain 5 | Networking and Content Delivery          | 10/12 | 83.33%  |
| Domain 6 | Cost and Performance Optimization        | 5/5   | 100%    |

## Domain 1: Monitoring, Logging, and Remediation

| No  |     | Q                                           | A                                                                                                                      | Ref               |
| --- | --- | ------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ----------------- |
|     |     |                                             |                                                                                                                        |                   |
| 1   |     |                                             |                                                                                                                        |                   |
| 2   |     |                                             |                                                                                                                        |                   |
| 3   |     |                                             |                                                                                                                        |                   |
| 4   |     |                                             |                                                                                                                        |                   |
| 5   | ❌  | Notify when EC2 underlying hardware failure | 1. CW `metric alarm` for EC2 metric: ~~`StatusCheckFailed_Instance`~~, `StatusCheckFailed_System`, `StatusCheckFailed` | [^1.5.1] [^1.5.2] |
|     |     |                                             | 2. SNS topic: subscribe emails                                                                                         | [^1.5.3]          |
|     |     |                                             | 3. Config the alarm action to send message to SNS topic                                                                |                   |
| 6   |     |                                             |                                                                                                                        |                   |
| 7   |     |                                             |                                                                                                                        |                   |
| 8   |     |                                             |                                                                                                                        |                   |
| 9   |     |                                             |                                                                                                                        |                   |
| 10  |     |                                             |                                                                                                                        |                   |
| 11  |     |                                             |                                                                                                                        |                   |
| 12  |     |                                             |                                                                                                                        |                   |
| 13  |     |                                             |                                                                                                                        |                   |
| 14  |     |                                             |                                                                                                                        |                   |

## Domain 2: Reliability and Business Continuity

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
| 9   |     |     |     |     |
| 10  |     |     |     |     |

## Domain 3: Deployment, Provisioning, and Automation

| No  |     | Q                 | A                                                                            | Ref                              |
| --- | --- | ----------------- | ---------------------------------------------------------------------------- | -------------------------------- |
|     |     |                   |                                                                              |                                  |
| 1   |     |                   |                                                                              |                                  |
| 2   |     |                   |                                                                              |                                  |
| 3   |     |                   |                                                                              |                                  |
| 4   |     |                   |                                                                              |                                  |
| 5   |     |                   |                                                                              |                                  |
| 6   |     |                   |                                                                              |                                  |
| 7   | ❌  | Tagging resources | 1. SGP tag polices: Standardize: -> organization-wide compliance report      | [^1.3.7.1] [^1.3.7.2]            |
|     |     |                   | 2. AWS Config `required-tags` -> Identify non-compliant tags -> Remediation? | [^1.3.7.3] [^1.3.7.4] [^1.3.7.5] |
| 8   |     |                   |                                                                              |                                  |
| 9   |     |                   |                                                                              |                                  |
| 10  |     |                   |                                                                              |                                  |
| 11  |     |                   |                                                                              |                                  |
| 12  |     |                   |                                                                              |                                  |
| 13  |     |                   |                                                                              |                                  |

## Domain 4: Security and Compliance

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
| 9   |     |     |     |     |
| 10  |     |     |     |     |
| 11  |     |     |     |     |

## Domain 5: Networking and Content Delivery

| No  |     | Q                                            | A                                                                                                    | Ref               |
| --- | --- | -------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ----------------- |
|     |     |                                              |                                                                                                      |                   |
| 1   |     |                                              |                                                                                                      |                   |
| 2   |     |                                              |                                                                                                      |                   |
| 3   | ❌  | CloudFront: Mismatch desktop/mobile version? | 1. Forward `User-Agent` to origin: CloudFront : Distribution : Origin Setting : Origin custom header | [^5.3.1] [^5.3.2] |
|     |     |                                              | 2. Cache based on the `User-Agent` header (not recommend) (or `CloudFront-Is-XXX-Viewer`)            | [^5.3.3]          |
| 4   |     |                                              |                                                                                                      |                   |
| 5   |     |                                              |                                                                                                      |                   |
| 6   |     |                                              |                                                                                                      |                   |
| 7   |     |                                              |                                                                                                      |                   |
| 8   | ❌  | EC2: Cannot connect to the instance?         | 1. SSH (22) or RDP (3389)                                                                            |                   |
|     |     |                                              | 2. NACL inbound & outbound allow?                                                                    |                   |
|     |     |                                              | 3. SG inbound allow?                                                                                 |                   |
| 9   |     |                                              |                                                                                                      |                   |
| 10  |     |                                              |                                                                                                      |                   |
| 11  |     |                                              |                                                                                                      |                   |
| 12  |     |                                              |                                                                                                      |                   |

## Domain 6: Cost and Performance Optimization

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   |     |     |     |     |
| 2   |     |     |     |     |
| 3   |     |     |     |     |
| 4   |     |     |     |     |
| 5   |     |     |     |     |

[^1.3.7.1]: <https://docs.aws.amazon.com/tag-editor/latest/userguide/tag-policies-orgs.html>
[^1.3.7.2]: <https://docs.aws.amazon.com/tag-editor/latest/userguide/tag-policies-orgs-evaluating-org-wide-compliance.html>
[^1.3.7.3]: <https://docs.aws.amazon.com/config/latest/developerguide/required-tags.html>
[^1.3.7.4]: <https://aws.amazon.com/blogs/devops/aws-config-checking-for-compliance-with-new-managed-rule-options/>
[^1.3.7.5]: <https://docs.aws.amazon.com/config/latest/developerguide/evaluating-your-resources.html>
[^1.5.1]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html>
[^1.5.2]: <https://aws.amazon.com/blogs/aws/ec2-instance-status-metrics/>
[^1.5.3]: <https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html#alarms-and-actions>
[^5.3.1]: <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/add-origin-custom-headers.html>
[^5.3.2]: <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/RequestAndResponseBehaviorCustomOrigin.html#request-custom-headers-behavior>
[^5.3.3]: <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/header-caching.html#header-caching-web-device>
