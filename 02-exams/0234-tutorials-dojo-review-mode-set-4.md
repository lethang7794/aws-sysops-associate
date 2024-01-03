# Tutorial Dojo - SOA-C02 - Review Mode Set 4

Test time: 00:47:03

Score: 61/65 (93.85%):

|          | Domain                                   | Score | Percent |
| -------- | ---------------------------------------- | ----- | ------- |
| Domain 1 | Monitoring, Logging, and Remediation     | 13/16 | 81.25%  |
| Domain 2 | Reliability and Business Continuity      | 8/8   | 100%    |
| Domain 3 | Deployment, Provisioning, and Automation | 15/16 | 93.75%  |
| Domain 4 | Security and Compliance                  | 14/14 | 100%    |
| Domain 5 | Networking and Content Delivery          | 8/8   | 100%    |
| Domain 6 | Cost and Performance Optimization        | 3/3   | 100%    |

## Domain 1: Monitoring, Logging, and Remediation

| No  |     | Q                                                                                             | A                                                                                                 | Ref |
| --- | --- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | --- |
|     |     |                                                                                               |                                                                                                   |     |
| 1   | ✅  |                                                                                               |                                                                                                   |     |
| 2   | ✅  |                                                                                               |                                                                                                   |     |
| 3   | ❌  | EC2: System check fail. Resolve?                                                              | Stop & relaunch (not ~~`reboot`~~, ~~`terminate`~~)                                               |     |
| 4   | ❌  | CW Logs: Detailed count of application errors, classified by type, across all log group. How? | `CW` **`Logs Insight`** + `stats` command + `count` function                                      |     |
| 5   | ✅  |                                                                                               |                                                                                                   |     |
| 6   | ❌  | EC2: Reboot instance if CPU is 100% for 3 mins. How?                                          | `Detailed monitoring` + `CW Alarm action` `Reboot`[^1.6.1] (`3 consecutive points` of `1 minute`) |     |
| 7   | ✅  |                                                                                               |                                                                                                   |     |
| 8   | ✅  |                                                                                               |                                                                                                   |     |
| 9   | ✅  |                                                                                               |                                                                                                   |     |
| 10  | ✅  |                                                                                               |                                                                                                   |     |
| 11  | ✅  |                                                                                               |                                                                                                   |     |
| 12  | ✅  |                                                                                               |                                                                                                   |     |
| 13  | ✅  |                                                                                               |                                                                                                   |     |
| 14  | ✅  |                                                                                               |                                                                                                   |     |
| 15  | ✅  |                                                                                               |                                                                                                   |     |
| 16  | ✅  |                                                                                               |                                                                                                   |     |

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

| No  |     | Q                                                 | A                                                                                     | Ref |
| --- | --- | ------------------------------------------------- | ------------------------------------------------------------------------------------- | --- |
|     |     |                                                   |                                                                                       |     |
| 1   | ✅  |                                                   |                                                                                       |     |
| 2   | ✅  |                                                   |                                                                                       |     |
| 3   | ✅  |                                                   |                                                                                       |     |
| 4   | ✅  |                                                   |                                                                                       |     |
| 5   | ✅  |                                                   |                                                                                       |     |
| 6   | ✅  |                                                   |                                                                                       |     |
| 7   | ✅  |                                                   |                                                                                       |     |
| 8   | ✅  |                                                   |                                                                                       |     |
| 9   | ❌  | EKS: Scale + Operational effective? Prerequisite? | Use K8s `Horizontal Pod AutoScaler` (which requires: `kubectl`, `K8s Metrics Server`) |     |
| 10  | ✅  |                                                   |                                                                                       |     |
| 11  | ✅  |                                                   |                                                                                       |     |
| 12  | ✅  |                                                   |                                                                                       |     |
| 13  | ✅  |                                                   |                                                                                       |     |
| 14  | ✅  |                                                   |                                                                                       |     |
| 15  | ✅  |                                                   |                                                                                       |     |

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

## Domain 6: Cost and Performance Optimization

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   | ✅  |     |     |     |
| 2   | ✅  |     |     |     |
| 3   | ✅  |     |     |     |

[^1.6.1]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/UsingAlarmActions.html#AddingRebootActions>
