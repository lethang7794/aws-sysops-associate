# Tutorial Dojo - SOA-C02 - Domain 4: Security and Compliance

YOUR TIME: 01:13:06

You have reached 17 of 27 point(s), (62.96%)

| No  |     | Q                                                                                                                             | A                                                                                                                                                                                          | Ref                 |
| --- | --- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------- |
|     |     |                                                                                                                               |                                                                                                                                                                                            |                     |
| 1   | ❌  | S3: Delete bucket (Versioning + MFA Delete)                                                                                   | [S3 Bucket Deletion](#41-s3-bucket-delete)                                                                                                                                                 |                     |
| 2   | ❌  | EB: CLI - "The instance profile aws-elasticbeanstalk-ec2-role associated with the environment does not exist". Why?           | 1. The CLI successfully called AWS. 2. Maybe the credential doesn't have permission to create an IAM Instance Role; 3. The IAM Instance Role doesn't have enough permissions to do its job |                     |
| 3   | ❌  | S3: Create, overwrite, and delete any object in an S3 bucket as well as to write additional ACL. Grant permissions with ACLs? | (S3 ACLs is now disabled for all new buckets) ACLs: `READ`, **`WRITE`**, `READ_ACP`, **`WRITE_ACP`**, `FULL_CONTROl`                                                                       | [^4.3] [^4.3.2]     |
| 4   | ✅  | RDS: Best practice for security.                                                                                              | VPC, IAM, SG, SSL, Encryption                                                                                                                                                              | [^4.4.1] [^4.4.2]   |
| 5   | ✅  | Multiple AWS accounts. Ensure certain services/actions are not allowed across all account. How?                               | Use AWS Organization + Service Control Policy (SCP)                                                                                                                                        |                     |
| 6   | ✅  | Provision SSL/TLS certificate. Which service?                                                                                 | AWS Certificate Manager                                                                                                                                                                    |                     |
| 7   | ✅  | Ensure RDS database credentials are not stored in plaintext & be rotated automatically. How?                                  | AWS Secrets Manager                                                                                                                                                                        |                     |
| 8   | ✅  | IT security compliance. Ensure all API calls are logs. How?                                                                   | AWS CloudTrail                                                                                                                                                                             |                     |
| 9   | ✅  | VPC Flow Logs show access to bastion host from unknown IP addresses. Why?                                                     | Maybe some instance use the same SG as the bastion host                                                                                                                                    |                     |
| 10  | ❌  | S3, CloudFront: Ensure data encryption                                                                                        | 1. Enforce HTTPS in CloudFront Viewer Origin Policy. 2. Use KMS to get data key & encrypt data before upload to S3 (provide the encrypted data key in header) (Envelope Encryption)        | [^4.10]             |
| 11  | ✅  | Report on activities on EC2 instances, communication with other services, running processes, network traffic?                 | [Security, Identity & Compliance on AWS](#411-security-identity--compliance-on-aws) Amazon Inspector: We investigated ourself & found we did nothing wrong (indeed it's best practice).    |                     |
| 12  | ✅  | Compliance reports: PCI...                                                                                                    | AWS Artifact                                                                                                                                                                               |                     |
| 13  | ✅  | On-premise AD. How to extend AD to AWS & control access to AWS?                                                               | Use `AWS Directory Service` (`AWS Managed Microsoft AD` - to connect with on-premises AD) & connect to `AWS IAM Identity Center` (SSO + assign permissions)                                |                     |
| 14  | ✅  | On-premise KMS. Migrate to AWS (FIPS 140-2 compliance). Which service?                                                        | CloudHSM (not ~~AWS KSM~~)                                                                                                                                                                 |                     |
| 15  | ❌  | Regular scan accounts for security standard: PCI DSS, CIS AWS                                                                 | AWS **Security Hub** (not ~~Inspector, Guard Duty, Macie, AWS Config~~)                                                                                                                    |                     |
| 16  | ❌  | Migrate to AWS: preserve security + give employees access to AWS resources. How to do it with IAM?                            | 1. Create IAM identity (User, Role, Group); 2. Assign IAM policy to these IAM identity                                                                                                     |                     |
| 17  | ✅  | Review existing cloud architecture with thousands of users/teams. Which IAM best practice?                                    | [Security best practice in IAM](#417-security-best-practices-in-iam)                                                                                                                       | [^4.17]             |
| 18  | ✅  | CloudTrail: Ensure logs are not tampered. How?                                                                                | Enable CloudTrail `Log file validation` (aka log file integrity validation)                                                                                                                | [^4.18]             |
| 19  | ✅  | S3: Sensitive data. Only privilege IAM users should have access + MFA. How to ensure?                                         | 1. Enable MFA for IAM user; 2. Add bucket policy to: allow access from privilege users (with MFA present)                                                                                  | [^4.19.1] [^4.19.2] |
| 20  | ✅  | SQL injection, XSS, DDoS. Which service?                                                                                      | AWS WAF + Shield                                                                                                                                                                           |                     |
| 21  | ❌  | RDS encryption                                                                                                                | [RDS Encryption](#421-rds-encryption)                                                                                                                                                      |                     |
| 22  | ❌  | IAM Policy                                                                                                                    | IAM Policy Statement: **P**_**EA**_**R** C 🍐👙 <br>(**Principal** - **_Effect_** - **_Action_** - **Resource** - Condition)                                                               | [^4.22]             |
| 23  | ✅  | Allow vendor access to AWS resources. Restrict to specific resources in a short-time (2 weeks). Which IAM Policy type to use? | Inline IAM Policy (not ~~AWS Managed Policy~~)                                                                                                                                             |                     |
| 24  | ✅  | RDS: Encryption in transit. How?                                                                                              | Use SSL to connect from application to RDS                                                                                                                                                 | [^4.24]             |
| 25  | ❌  | S3: Read/write but not delete objects. How?                                                                                   | Attach an IAM Policy with 2 statement: allow read/write, deny delete.                                                                                                                      |                     |
| 26  | ❌  | RDS: Find sensitive data. How?                                                                                                | Use Macie (to discover sensitive data in S3) + DMS (to export data from RDS to S3)                                                                                                         | [^4.26]             |
| 27  | ✅  | Allow audit team to access log file of all resources?                                                                         | Use CloudTrail + Give read access to S3 bucket that stores CloudTrail logs                                                                                                                 | [^4.27]             |

[^4.3]: <https://aws.amazon.com/about-aws/whats-new/2023/04/amazon-s3-security-best-practices-buckets-default/>
[^4.3.2]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/acl-overview.htmsl>
[^4.4.1]: <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.html>
[^4.4.2]: <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.html>
[^4.17]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html>
[^4.18]: <https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-log-file-validation-intro.html>
[^4.19.1]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html#example-bucket-policies-MFA>
[^4.19.2]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_configure-api-require.html#MFAProtectedAPI-resource-policies>
[^4.22]: <https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#access_policies-json>
[^4.24]: <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.SSL.html>
[^4.26]: <https://aws.amazon.com/blogs/security/enabling-data-classification-for-amazon-rds-database-with-amazon-macie/>
[^4.27]: <https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html>

## 4.1 S3 Bucket Delete

You can only delete buckets that don't have any objects in them [^4.1.1].

> [!Note]
> In a versioning bucket, objects can have delete markers & multiple variants.

For a versioning bucket, to _permanently_ delete an object, all versions of that object needs to be deleted first. This can be done with:

- Manually via Web Console
- SDK
- Life-cycle methods [^4.1.2]

  - `Expiration`: Expire current object versions

    Retains the current version as noncurrent version then add a `delete marker`, which becomes the current version)

  - `NoncurrentVersionExpiration`: Permanently remove noncurrent object versions

> [!NOTE]
> MFA delete [^4.1.3] requires additional authentication for either of the following operations:
>
> - Changing the versioning state of your bucket
> - Permanently deleting an object version

If a bucket's versioning configuration is MFA delete enabled, the bucket owner must include the `x-amz-mfa` [^4.1.4] request header in requests to

- change the versioning state of the bucket.
- permanently delete an object version or

[^4.1.1]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/delete-bucket.html>
[^4.1.2]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/DeletingObjectVersions.html>
[^4.1.3]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/MultiFactorAuthenticationDelete.html>
[^4.1.4]: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/UsingMFADelete.html>
[^4.10]: <https://docs.aws.amazon.com/amazon-s3-encryption-client/latest/developerguide/concepts.html#envelope-encryption>

## 4.11 Security, Identity & Compliance on AWS

| Category                         | AWS Service                                | ELI5                                               | What is it                                                                              |
| -------------------------------- | ------------------------------------------ | -------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Identity & Access Management     | AWS IAM                                    |                                                    | Securely manage identities and access to AWS services and resources                     |
|                                  | AWS IAM Identity Center (successor to SSO) |                                                    | Centrally manage workforce access to multiple AWS accounts and applications             |
|                                  | Amazon Cognito                             |                                                    | Implement secure, frictionless customer identity and access management that scales      |
|                                  | AWS Directory Service                      |                                                    | Gain efficiency with a fully managed Microsoft Active Directory service                 |
|                                  | AWS Organizations                          |                                                    | Centrally manage your environment as you scale your AWS resources                       |
| Detection & Response             | Amazon GuardDuty                           | 👮🔦📜 Protect against external threats -> 🛂      | Protect AWS accounts with intelligent threat detection                                  |
|                                  | Amazon Inspector                           | 🖥️🕳️🚪 Investigate ourself (nothing's wrong) -> 🩹 | Automated and continual vulnerability management at scale                               |
|                                  | AWS Security Hub                           | Do we pass industry standards (PCI, CIS)?          | Automate AWS security checks and centralize security alerts                             |
|                                  | Amazon Detective                           |                                                    | Analyze and visualize security data to investigate potential security issues            |
|                                  | AWS Config                                 | This is the config I want                          | Assess, audit, and evaluate configurations of your resources                            |
|                                  | Amazon CloudWatch                          | What's happing with my applications (on AWS)?      | Observe and monitor resources and applications on AWS, on premises, and on other clouds |
|                                  | AWS CloudTrail                             | What's happening with my AWS resources?            | Track user activity and API usage                                                       |
| Network & Application Protection | AWS Firewall Manager                       |                                                    | Centrally configure and manage firewall rules across your accounts                      |
|                                  | AWS Network Firewall                       |                                                    | Deploy network firewall security across your VPCs                                       |
|                                  | AWS Shield                                 | 🛡️ DDoS                                            | Maximize application availability and responsiveness with managed DDoS protection       |
|                                  | AWS Web Application Firewall (WAF)         | SQL injection, XSS                                 | Protect your web applications from common exploits                                      |
| Data Protection                  | Amazon Macie                               | Any Credit Card here? 🪣                           | Discover and protect your sensitive data at scale                                       |
|                                  | AWS Key Management Service (KMS)           | 🔐                                                 | Create and control keys to encrypt or digitally sign your data                          |
|                                  | AWS CloudHSM                               | 🏰                                                 | Manage single-tenant hardware security modules (HSMs) on AWS                            |
|                                  | AWS Certificate Manager                    | 🗃️                                                 | Provision and manage SSL/TLS certificates with AWS services and connected resources     |
|                                  | AWS Secrets Manager                        |                                                    | Centrally manage the lifecycle of secrets                                               |
| Compliance                       | AWS Artifact                               | 🗞️ PCI...                                          | No cost, self-service portal for on-demand access to AWS’ compliance reports            |
|                                  | AWS Audit Manager                          |                                                    | Continually audit your AWS usage to simplify risk and compliance assessment             |

## 4.17 [Security Best Practices in IAM]

- Follow best practices to protect your **root user** credentials
- Require multi-factor authentication (**MFA**)
- Require human users 👪 to use federation with an identity provider to access AWS using _temporary credentials_
- Require workloads 💻 to use _temporary credentials_ with IAM roles to access AWS
- For use cases 🪨 that require _long-term credentials_ , update (& remove) access keys when needed
- Apply **least-privilege** 🤏 permissions
  - Get started with _AWS managed policies_ and move toward least-privilege permissions
  - Use _conditions_ in IAM policies to further restrict access
- Regularly review and remove unused users, roles, permissions, policies, and credentials
- Use IAM Access Analyzer to
  - Generate least-privilege policies based on access activity
  - Verify public and cross-account access to resources
  - Validate your IAM policies to ensure secure and functional permissions
- Limit permission for
  - An account 🛟 👈 Permissions boundaries
  - Multiple accounts 🦺🛥️ 👈 AWS Organization + Service Control Policies (SCP)

[Security Best Practices in IAM]: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html

## 4.21 [RDS Encryption]

Encrypting a RDS instance is a one-way decision that needs to be make when creating the instance.

- You can't (directly) **turn on** encryption on an un-encrypted RDS instance.

> [!TIP]
> What if you've already have un-encrypted RDS instance?
>
> 1. Create a snapshot of the un-encrypted RDS instance.
> 2. Create an encrypted copy of that un-encrypted snapshot.
> 3. Restore a DB instance from that encrypted snapshot.

- You can't (directly)
  - **turn off** encryption on an encrypted RDS instance.
  - **un-encrypt** an encrypted RDS instance.

> [!TIP]
> What if you really need to remove the encryption from a RDS instance?
>
> 1. Export data from an encrypted DB instance.
> 2. Import the data into an unencrypted DB instance.

Snapshots, read replicas (of an encrypted RDS instance) use the same encryption key as the source.

> [!TIP]
> If it's in a different region, you need to specify the KMS key in the destination region.

[RDS Encryption]: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html#Overview.Encryption.Enabling
