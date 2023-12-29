# Tutorial Dojo - SOA-C02 - Timed Mode Set 5

Test time: 00:36:49

Score: 58/65 (89%):

|          | Domain                                   | Score | Percent |
| -------- | ---------------------------------------- | ----- | ------- |
| Domain 1 | Monitoring, Logging, and Remediation     | 8/10  | 80%     |
| Domain 2 | Reliability and Business Continuity      | 5/6   | 83.33%  |
| Domain 3 | Deployment, Provisioning, and Automation | 14/16 | 87.5%   |
| Domain 4 | Security and Compliance                  | 16/16 | 100%    |
| Domain 5 | Networking and Content Delivery          | 9/9   | 100%    |
| Domain 6 | Cost and Performance Optimization        | 6/8   | 75%     |

## Domain 1: Monitoring, Logging, and Remediation

| No  |     | Q                                                                           | A                                                                                                                              | Ref |
| --- | --- | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | --- |
|     |     |                                                                             |                                                                                                                                |     |
| 1   | ✅  |                                                                             |                                                                                                                                |     |
| 2   | ✅  |                                                                             |                                                                                                                                |     |
| 3   | ✅  |                                                                             |                                                                                                                                |     |
| 4   | ✅  |                                                                             |                                                                                                                                |     |
| 5   | ✅  |                                                                             |                                                                                                                                |     |
| 6   | ✅  |                                                                             |                                                                                                                                |     |
| 7   | ✅  |                                                                             |                                                                                                                                |     |
| 8   | ✅  |                                                                             |                                                                                                                                |     |
| 9   | ❌  | RDS: Check OS patch process. How?                                           | AWS Management Console: RDS : RDS instance detail page: Tab `Maintenance & backups`[^1.9.1]                                    |     |
| 10  | ❌  | Track usage of cloud resources against AWS service limit. Notify via Slack. | Implement a **Quota Monitor for AWS**[^1.10.1] with: 1. AWS `Trusted Adviser` : `Service Limit`; 2. `EventBridge`; 3. `Lambda` |     |

## Domain 2: Reliability and Business Continuity

| No  |     | Q                                                                                | A                                                                               | Ref |
| --- | --- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | --- |
|     |     |                                                                                  |                                                                                 |     |
| 1   | ❌  | OpenSearch Service: How many master nodes & storage nodes for high availability? | For HA, OpenSearch Service recommends 3 AZs[^2.1.0] with 3 master nodes[^2.1.1] |     |
| 2   | ✅  |                                                                                  |                                                                                 |     |
| 3   | ✅  |                                                                                  |                                                                                 |     |
| 4   | ✅  |                                                                                  |                                                                                 |     |
| 5   | ✅  |                                                                                  |                                                                                 |     |
| 6   | ✅  |                                                                                  |                                                                                 |     |

## Domain 3: Deployment, Provisioning, and Automation

| No  |     | Q                                                              | A                                                                                                  | Ref |
| --- | --- | -------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | --- |
|     |     |                                                                |                                                                                                    |     |
| 1   | ✅  |                                                                |                                                                                                    |     |
| 2   | ✅  |                                                                |                                                                                                    |     |
| 3   | ✅  |                                                                |                                                                                                    |     |
| 4   | ✅  |                                                                |                                                                                                    |     |
| 5   | ✅  |                                                                |                                                                                                    |     |
| 6   | ✅  |                                                                |                                                                                                    |     |
| 7   | ✅  |                                                                |                                                                                                    |     |
| 8   | ❌  | ASG (EC2): Reduce boot-up time?                                | 1. EC2: Bake AMI (with EC2 Image Builder); 2. ASG: Create a warm pool                              |     |
| 9   | ✅  |                                                                |                                                                                                    |     |
| 10  | ✅  |                                                                |                                                                                                    |     |
| 11  | ✅  |                                                                |                                                                                                    |     |
| 12  | ❌  | Cfn: VPC, EC2, RDS, IGW. How to prevent errors when deploying? | VPC needs to be created first, RDS needs to be created before EC2 ... -> Use `DependsOn` attribute |     |
| 13  | ✅  |                                                                |                                                                                                    |     |
| 14  | ✅  |                                                                |                                                                                                    |     |
| 15  | ✅  |                                                                |                                                                                                    |     |
| 16  | ✅  |                                                                |                                                                                                    |     |

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

| No  |     | Q                                                                            | A                                                                                                                                                                          | Ref |
| --- | --- | ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
|     |     |                                                                              |                                                                                                                                                                            |     |
| 1   | ❌  | Backup solution: Access within minutes for 6 months, available for 10 years. | File Gateway (not Tape Gateway. Why?) + Lifecycle method                                                                                                                   |     |
| 2   | ✅  |                                                                              |                                                                                                                                                                            |     |
| 3   | ❌  | Elasticache: Vertical scaling? Online/Offline?                               | Elasticache for Redis: supports 1. Auto Scaling[^6.3.1] Shards/Replicas; 2a. Offline/online re-sharding[^6.3.2]; 2b. Online vertical scaling[^6.3.3]                       |     |
|     |     |                                                                              | Elasticache for Memcached scaling:[^6.3.4] 1. Horizontally scaling (add/remove nodes); 2. (Offline) Vertical scaling (Replace new cluster with higher/lower instance type) |     |
| 4   | ✅  |                                                                              |                                                                                                                                                                            |     |
| 5   | ✅  |                                                                              |                                                                                                                                                                            |     |
| 6   | ✅  |                                                                              |                                                                                                                                                                            |     |
| 7   | ✅  |                                                                              |                                                                                                                                                                            |     |
| 8   | ✅  |                                                                              |                                                                                                                                                                            |     |

## 6.3 Elasticache

ElastiCache[^6.3.0] supports 2 engine:

- Redis
- Memcached

ElastiCache supports 2 deployment options:

- Serverless: no worrying about capacity planning, hardware management, or cluster design

- Self-design cluster: You design your own cluster: node family, size, number of nodes (shards for Redis)

  You

  - manually scale your cluster

    - Vertical scaling: by increasing or decreasing the cache node size when needed.
    - Horizontal scaling: by adding new shards or adding more replicas to your shards.

  - use Auto-Scaling (for Shards/Replicas) with 2 type of scaling polices:

    - Target tracking scaling
    - Scheduled scaling

[^6.3.0]: <https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/WhatIs.corecomponents.html>
[^6.3.1]: <https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/AutoScaling.html>
[^6.3.2]: <https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/redis-cluster-resharding-online.html>
[^6.3.3]: <https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/redis-cluster-vertical-scaling.html>
[^6.3.4]: <https://docs.aws.amazon.com/AmazonElastiCache/latest/mem-ug/Scaling-self-designed.html>
[^1.9.1]: <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_UpgradeDBInstance.Maintenance.html>
[^1.10.1]: <https://aws.amazon.com/solutions/implementations/quota-monitor/>
[^2.1.0]: <https://aws.amazon.com/blogs/big-data/configure-amazon-opensearch-service-for-high-availability/>
[^2.1.1]: <https://docs.aws.amazon.com/opensearch-service/latest/developerguide/managedomains-dedicatedmasternodes.html>
