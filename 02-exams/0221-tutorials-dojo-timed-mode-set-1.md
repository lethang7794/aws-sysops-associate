# Tutorial Dojo - SOA-C02 - Timed Mode Set 1

Test time: 1h

Score: 56/65 (86%):

|          | Domain                                   | Score | Percent |
| -------- | ---------------------------------------- | ----- | ------- |
| Domain 1 | Monitoring, Logging, and Remediation     | 12/14 | 85.71%  |
| Domain 2 | Reliability and Business Continuity      | 10/10 | 100%    |
| Domain 3 | Deployment, Provisioning, and Automation | 13/13 | 100%    |
| Domain 4 | Security and Compliance                  | 5/11  | 45.45%  |
| Domain 5 | Networking and Content Delivery          | 11/12 | 91.67%  |
| Domain 6 | Cost and Performance Optimization        | 5/5   | 100%    |

## Domain 1: Monitoring, Logging, and Remediation

| No  |     | Q                                                                                                                       | A                                                                         | Ref                                                 |
| --- | --- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | --------------------------------------------------- |
|     |     |                                                                                                                         |                                                                           |                                                     |
| 1   | ❌  | Notify teams in the event that the resource utilization (of their teams) exceeded the defined threshold. Which service? | AWS Budgets (CloudWatch Billing Alarm only monitor account-level billing) |                                                     |
| 2   | ✅  |                                                                                                                         |                                                                           |                                                     |
| 3   | ✅  |                                                                                                                         |                                                                           |                                                     |
| 4   | ✅  |                                                                                                                         |                                                                           |                                                     |
| 5   | ✅  |                                                                                                                         |                                                                           |                                                     |
| 6   | ❌  | EFS: `PercentIOLimit` 100%: Poor performance. Ensure high throughput, IOPS?                                             | [EFS performance & migration](#i16-efs-performance)                       | Metrics for EFS[^I.1.6.1] EFS performance[^I.1.6.2] |
| 7   | ✅  |                                                                                                                         |                                                                           |                                                     |
| 8   | ✅  |                                                                                                                         |                                                                           |                                                     |
| 9   | ✅  |                                                                                                                         |                                                                           |                                                     |
| 10  | ✅  |                                                                                                                         |                                                                           |                                                     |
| 11  | ✅  |                                                                                                                         |                                                                           |                                                     |
| 12  | ✅  |                                                                                                                         |                                                                           |                                                     |
| 13  | ✅  |                                                                                                                         |                                                                           |                                                     |
| 14  | ✅  |                                                                                                                         |                                                                           |                                                     |

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
| 10  | ✅  |     |     |     |

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
| 13  | ✅  |     |     |     |

## Domain 4: Security and Compliance

| No  |     | Q                                                                                         | A                                                                                                                                                                                                                                                            | Ref                                                                |
| --- | --- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------ |
|     |     |                                                                                           |                                                                                                                                                                                                                                                              |                                                                    |
| 1   | ❌  | IAM accounts: Sign-in? Can multiple IAM from multiple accounts use the same URL?          | [IAM users sign in](#i41-iam-users-sign-in)                                                                                                                                                                                                                  |                                                                    |
| 2   | ✅  |                                                                                           |                                                                                                                                                                                                                                                              |                                                                    |
| 3   | ✅  |                                                                                           |                                                                                                                                                                                                                                                              |                                                                    |
| 4   | ✅  |                                                                                           |                                                                                                                                                                                                                                                              |                                                                    |
| 5   | ❌  | SG: Allow public SSH inbound traffic. Automatically identify & block publish SSH ports?   | AWS Config applies remediation (to remediate non-compliant resources) using AWS Systems Manager Automation documents                                                                                                                                         | Remediation action [^I.4.5]                                        |
| 6   | ❌  | EBS: Encrypt all volume in multi regions. Enforce (automatically) for new EBS volume?     | EBS encryption can be enabled at: 1. Region-level (called `Encryption by default`)[^I.4.6.1]; 2. Volume/snapshot level                                                                                                                                       | [^I.4.6.2] TODO: check RDS, S3, ...                                |
| 7   | ✅  |                                                                                           |                                                                                                                                                                                                                                                              |                                                                    |
| 8   | ❌  | S3: Restrict access to objects?                                                           | 1. ACLs (works at object/bucket level, not supports fine-grain permission) ; 2. Bucket policy (works at bucket-level, supports fine-grain permission); 3. S3 Access Grants (works at region-level, supports supports fine-grain permission, e.g. prefix URI) | ACL[^I.4.8.1], Bucket-policy[^I.4.8.2], S3 Access Grants[^I.4.8.3] |
| 9   | ✅  |                                                                                           |                                                                                                                                                                                                                                                              |                                                                    |
| 10  | ❌  | Multi account: Preview changes to permission, finding all external access. Which service? | IAM Access Analyzer (more features than IAM Policy Simulator)                                                                                                                                                                                                |                                                                    |
| 11  | ❌  | KMS: Imported key: Rotate every 6 months?                                                 | [Rotating AWS KMS Keys](#i411-rotating-aws-kms-keys)                                                                                                                                                                                                         |                                                                    |

## Domain 5: Networking and Content Delivery

| No  |     | Q                                                                     | A                  | Ref |
| --- | --- | --------------------------------------------------------------------- | ------------------ | --- |
|     |     |                                                                       |                    |     |
| 1   | ✅  |                                                                       |                    |     |
| 2   | ✅  |                                                                       |                    |     |
| 3   | ✅  |                                                                       |                    |     |
| 4   | ✅  |                                                                       |                    |     |
| 5   | ✅  |                                                                       |                    |     |
| 6   | ✅  |                                                                       |                    |     |
| 7   | ✅  |                                                                       |                    |     |
| 8   | ❌  | Flow logs: ... XXX.XXX.XXX.XXX YYY.YYY.YYY.YYY ZZZ 3389 ... REJECT OK | 3389: RDP; 22: SSH |     |
| 9   | ✅  |                                                                       |                    |     |
| 10  | ✅  |                                                                       |                    |     |
| 11  | ✅  |                                                                       |                    |     |
| 12  | ✅  |                                                                       |                    |     |

## Domain 6: Cost and Performance Optimization

| No  |     | Q   | A   | Ref |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
| 1   | ✅  |     |     |     |
| 2   | ✅  |     |     |     |
| 3   | ✅  |     |     |     |
| 4   | ✅  |     |     |     |
| 5   | ✅  |     |     |     |

## I.1.6 EFS performance

Configuration impact an EFS performance:

- Storage Class:

  - EFS `One Zone` / One Zone-IA
  - **EFS `Standard`** / Standard-IA
  - EFS `Archive`

- Performance Mode:

  - **`General Purpose` mode** (default - 99.9% of uses): Lowest latency
  - `Max I/O` mode: Highly parallelized workloads that can tolerate higher latencies

- Throughput Mode:

  - `Bursting` mode: Throughput scale with storage
  - Enhanced
    - **`Elastic` mode** (default - recommend): Spiky/unpredictable workloads
    - `Provisioned` mode: Known performance requirements; or throughput > 5% average-to-peak ratio

To change performance mode, you need to:

- Create a new EFS file system
- Transfer data from old EFS file system to the new one (with AWS DataSync)

## I.4.1 IAM users sign in

IAM users in an AWS account sign in using a web URL that includes the `account ID`[^I.4.1.1] (called `Sign-in URL for IAM users`):

> [!TIP]
> The `Sign-in URL for IAM users` has the following format:
> `https://Your_Account_ID.signin.aws.amazon.com/console/`

If you don't have the URL, the _AWS sign-in page_ requires that you provide either the AWS `account ID`or its `account alias`.

> [!TIP]
> The AWS sign-in page[^I.4.1.2] URL:
> `https://console.aws.amazon.com/`

With `account alias`, you can contain your company name (or other friendly identifier) in the `Sign-in URL for IAM users`[^I.4.1.3]:

> [!TIP]
> A friendly `Sign-in URL for IAM users` with account alias
> `https://Your_Account_Alias.signin.aws.amazon.com/console/`

## I.4.11 Rotating AWS KMS Keys

Automatic key rotation is supported only on **_symmetric_ encryption KMS keys**[^I.4.11.0][^I.4.11.1] with _key material from AWS KMS_ (Origin = AWS_KMS[^I.4.11.2]).

Automatic key rotation is not supported on the following types of KMS keys, but you can rotate these KMS keys manually.

- _Asymmetric_ KMS keys
- HMAC KMS keys
- _symmetric_ encryption KMS keys with imported key material ("Bring your own key — BYOK")
- _symmetric_ encryption KMS keys in custom key stores (CloudHSM or "Hold your own key — HYOK")

[^I.1.6.1]: <https://docs.aws.amazon.com/efs/latest/ug/efs-metrics.html>
[^I.1.6.2]: <https://docs.aws.amazon.com/efs/latest/ug/performance.html>
[^I.4.1.1]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/console_account-alias.html>
[^I.4.1.2]: <https://aws.amazon.com/blogs/security/now-available-improvements-to-how-you-sign-in-to-your-aws-account/>
[^I.4.1.3]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/console_account-alias.html#AboutAccountAlias>
[^I.4.5]: <https://docs.aws.amazon.com/config/latest/developerguide/remediation.html>
[^I.4.6.1]: <https://aws.amazon.com/blogs/aws/new-opt-in-to-default-encryption-for-new-ebs-volumes/>
[^I.4.6.2]: <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html#encryption-by-default>
[^I.4.8.1]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/acls.html>
[^I.4.8.2]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-policies.html>
[^I.4.8.3]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-grants.html>
[^I.4.11.0]: <https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html#create-key-table>
[^I.4.11.1]: <https://docs.aws.amazon.com/kms/latest/developerguide/rotate-keys.html#rotate-keys-how-it-works>
[^I.4.11.2]: <https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#key-origin>
