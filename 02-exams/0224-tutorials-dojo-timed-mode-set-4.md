# Tutorial Dojo - SOA-C02 - Timed Mode Set 4

Test time: 00:47:03

Score: 62/65 (95%):

|          | Domain                                   | Score | Percent |
| -------- | ---------------------------------------- | ----- | ------- |
| Domain 1 | Monitoring, Logging, and Remediation     | 16/16 | 100%    |
| Domain 2 | Reliability and Business Continuity      | 8/8   | 100%    |
| Domain 3 | Deployment, Provisioning, and Automation | 15/16 | 93.75%  |
| Domain 4 | Security and Compliance                  | 13/14 | 92.86%  |
| Domain 5 | Networking and Content Delivery          | 7/8   | 87.5%   |
| Domain 6 | Cost and Performance Optimization        | 3/3   | 100%    |

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
| 14  | ✅  |     |     |     |
| 15  | ✅  |     |     |     |
| 16  | ✅  |     |     |     |

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

## Domain 3: Deployment, Provisioning, and Automation

| No  |     | Q                                        | A                                                                                                    | Ref |
| --- | --- | ---------------------------------------- | ---------------------------------------------------------------------------------------------------- | --- |
|     |     |                                          |                                                                                                      |     |
| 1   | ✅  |                                          |                                                                                                      |     |
| 2   | ✅  |                                          |                                                                                                      |     |
| 3   | ✅  |                                          |                                                                                                      |     |
| 4   | ✅  |                                          |                                                                                                      |     |
| 5   | ✅  |                                          |                                                                                                      |     |
| 6   | ❌  | ALB + CloudFront: User log out randomly? | 1. Use [Stickiness session](#36-stickiness-session); 2. Config CloudFront to forward cookies[^3.6.0] |     |
| 7   | ✅  |                                          |                                                                                                      |     |
| 8   | ✅  |                                          |                                                                                                      |     |
| 9   | ✅  |                                          |                                                                                                      |     |
| 10  | ✅  |                                          |                                                                                                      |     |
| 11  | ✅  |                                          |                                                                                                      |     |
| 12  | ✅  |                                          |                                                                                                      |     |
| 13  | ✅  |                                          |                                                                                                      |     |
| 14  | ✅  |                                          |                                                                                                      |     |
| 15  | ✅  |                                          |                                                                                                      |     |

## Domain 4: Security and Compliance

| No  |     | Q                                                                       | A                                                                   | Ref |
| --- | --- | ----------------------------------------------------------------------- | ------------------------------------------------------------------- | --- |
|     |     |                                                                         |                                                                     |     |
| 1   | ❌  | AD: ADFS: Login to Amazon OpenSearch Service using credentials from AD? | Use Cognito Identity Pool (Identity Federation), use ADFS as an IdP |     |
| 2   | ✅  |                                                                         |                                                                     |     |
| 3   | ✅  |                                                                         |                                                                     |     |
| 4   | ✅  |                                                                         |                                                                     |     |
| 5   | ✅  |                                                                         |                                                                     |     |
| 6   | ✅  |                                                                         |                                                                     |     |
| 7   | ✅  |                                                                         |                                                                     |     |
| 8   | ✅  |                                                                         |                                                                     |     |
| 9   | ✅  |                                                                         |                                                                     |     |
| 10  | ✅  |                                                                         |                                                                     |     |
| 11  | ✅  |                                                                         |                                                                     |     |
| 12  | ✅  |                                                                         |                                                                     |     |
| 13  | ✅  |                                                                         |                                                                     |     |
| 14  | ✅  |                                                                         |                                                                     |     |

## Domain 5: Networking and Content Delivery

| No  |     | Q                                                                                            | A                                                                                                                                                                                                                  | Ref |
| --- | --- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --- |
|     |     |                                                                                              |                                                                                                                                                                                                                    |     |
| 1   | ✅  |                                                                                              |                                                                                                                                                                                                                    |     |
| 2   | ✅  |                                                                                              |                                                                                                                                                                                                                    |     |
| 3   | ✅  |                                                                                              |                                                                                                                                                                                                                    |     |
| 4   | ✅  |                                                                                              |                                                                                                                                                                                                                    |     |
| 5   | ✅  |                                                                                              |                                                                                                                                                                                                                    |     |
| 6   | ✅  |                                                                                              |                                                                                                                                                                                                                    |     |
| 7   | ✅  |                                                                                              |                                                                                                                                                                                                                    |     |
| 8   | ❌  | EC2: Windows AMI: Cannot connect to the instance via RDP, other instances can. Troubleshoot? | Something's wrong with the instance. Use `EC2Rescue` for Windows[^5.8.1]/Linux[^5.8.2] on "unreachable instances"[^5.8.3] (using Systems Manager **Automation** to fix issues on the instance root volume[^5.8.4]) |     |

## Domain 6: Cost and Performance Optimization

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   | ✅  |     |     |     |
| 2   | ✅  |     |     |     |
| 3   | ✅  |     |     |     |

## 3.6 Stickiness session

ELB supports 2 strategies of stickiness:[^3.6.1]

1. `Sticky sessions`: route traffic to the same **target** (e.g. EC2 instance)

   > [!IMPORTANT]
   > How the ELB know which target/target group to send traffic to the same one?
   >
   > - It's cookies.
   > - To use sticky sessions, the client must support cookies.

   2 types of sticky sessions:

   - `Duration-based stickiness` (aka `load-balancer stickiness`):[^3.6.2] routes requests to the same target in a target group 👈 using a `load balancer generated cookie` named `AWSALB`
   - `Application-based stickiness`:[^3.6.3] routes the first request to a target within the target group based on the chosen algorithm 👈 using `application-based cookie`

2. `Target group stickiness`:[^3.6.4][^3.6.5] route traffic to the same ELB's **target group** (e.g. same version of application in blue-green deployment) 👈 using a `load balancer generated cookie` named `AWSALBTG`

[^3.6.0]: <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Cookies.html>
[^3.6.1]: <https://docs.aws.amazon.com/prescriptive-guidance/latest/load-balancer-stickiness/welcome.html>
[^3.6.2]: <https://docs.aws.amazon.com/elasticloadbalancing/latest/application/sticky-sessions.html#duration-based-stickiness>
[^3.6.3]: <https://docs.aws.amazon.com/elasticloadbalancing/latest/application/sticky-sessions.html#application-based-stickiness>
[^3.6.4]: <https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html#forward-actions>
[^3.6.5]: <https://docs.aws.amazon.com/prescriptive-guidance/latest/load-balancer-stickiness/target-group-stickiness.html>
[^5.8.1]: <https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/Windows-Server-EC2Rescue.html>
[^5.8.2]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Linux-Server-EC2Rescue.html>
[^5.8.3]: <https://docs.aws.amazon.com/systems-manager/latest/userguide/automation-ec2rescue.html>
[^5.8.4]: <https://docs.aws.amazon.com/systems-manager/latest/userguide/automation-ec2rescue.html#automation-ec2rescue-how>
