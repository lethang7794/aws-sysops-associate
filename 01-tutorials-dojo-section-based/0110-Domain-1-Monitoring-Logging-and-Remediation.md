# Tutorial Dojo - SOA-C02 - Domain 1: Monitoring, Logging, and Remediation

YOUR TIME: 01:34:33
You have reached 23 of 30 point(s), (76.67%)

| No  |     | Q                                                                                                      | A                                                                                                                                                                                       | Ref                      |
| --- | --- | ------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------ |
|     |     |                                                                                                        |                                                                                                                                                                                         |                          |
| 1   | ✅  | Cfn: Central config for AMI                                                                            | **System Manager** _Parameter Store_                                                                                                                                                    |                          |
| 2   | ✅  | EC2: NACL, SG. User cannot access. Which service to use for investigating?                             | VPC Flow Logs (logging IP traffic)                                                                                                                                                      |                          |
| 3   | ✅  | CL Logs: EC2. Installed CW Agent. No logs. Why?                                                        | Maybe not enough permissions to send logs to CW Logs -> Give the EC2 Instance Role enough permissions (`logs:PutLogEvents`, `logs:DescribeLogStreams`...)                               | [1.3]                    |
| 4   | ✅  | EC2: Monitor CPU Utilization of each process. How?                                                     | Use CW Agent + `procstat` plugin                                                                                                                                                        | [1.4.1] [1.4.2]          |
| 5   | ✅  | Create a dashboard for `CPUUtilization`, `DiskReadOps`, `NetworkIn`... (1-min interval)                | 1. Set up a CloudWatch dashboard; 2. Enable ~~`Basic monitoring`~~/`Detailed monitoring`                                                                                                | [1.5.1] [1.5.2] [1.5.3]  |
| 6   | ✅  | Route53 Health Check                                                                                   | Route 53 supports 3 type of health checks: 1. Check an endpoint; 2. Check check health check; 3. Check a CW alarm                                                                       |                          |
| 7   | ❌  | Send event notification for all system alerts to phones/emails. Which service?                         | SNS                                                                                                                                                                                     |                          |
| 8   | ✅  | CloudWatch: Collect custom metrics (& view visually).                                                  | You can publish your own metrics to CloudWatch using the AWS CLI or an API. You can view statistical graphs of your published metrics with the AWS Management Console.                  | [1.8]                    |
| 9   | ✅  | RDS: Monitor CPU/memory of each process on DB instance                                                 | Enable `RDS - Enhanced Monitoring` -> RDS instance **OS metric** (# `EC2 - Detailed Monitoring` -> **1-min period** instead of 5-min period)                                            | [1.9]                    |
| 10  | ✅  | ELB: Monitor IP address, latencies, request paths, server response?                                    | ELB Access Logs (disabled by default)                                                                                                                                                   | [1.10]                   |
| 11  | ✅  | EC2: Monitor memory                                                                                    | Use CloudWatch Agent + Custom metrics (`mem_available`, `mem_cached`, `mem_active`...)                                                                                                  |                          |
| 12  | ❌  | CloudFront: Reports                                                                                    | CloudFront supports 5 type of reports                                                                                                                                                   | [1.12]                   |
| 13  | ✅  | EC2: SSH port should NOT be opened publicly. How to send notification when an instance doesn't follow? | 1. Use AWS Config; 2. Create a AWS Config rule (SG not open SSH port); 3. Config AWS Config to to send a notification to SNS when the resources are not compliant with AWS Config rule. | [1.13]                   |
| 14  | ✅  | EC@: Maximum disk space allocated. How tho prevent?                                                    | 1. Use CloudWatch Agent; 2. Config CW Agent to collect disk metrics; 3. Create CW Alarm to watch disk metrics, base on the value & threshold, send a notification to SNS                | [1.14]                   |
| 15  | ✅  | Notify of any issues that occur in the underlying hardware that hosts your AWS resources               | Use AWS **_Personal_ Health Dashboard** + EventBridge rule. (Web Console / `AWS Health Dashboard` / `Your account health`) (Or use `AWS User Notifications`)                            | [1.15] [1.15.2] [1.15.3] |
| 16  | ✅  | Notify of any outages or any underlying infrastructure changes that AWS has made                       | Use AWS **Health Dashboard** + EventBridge rule. (Web Console / `AWS Health Dashboard` / `Service health`) (Or use `AWS User Notifications`)                                            |                          |
| 17  | ❌  | IAM Identity Center: How to give permissions to access AWS services?                                   | 1. Config permissions set(s); 2. Assign permission set(s) to a IAM Identity user/group                                                                                                  | [1.17]                   |
| 18  | ✅  | Notify - via Slack - of any outage of AWS region                                                       | Use AWS **Health Dashboard** (Service health) + EventBridge rule + Lambda (send notification to Slack)                                                                                  |                          |
| 19  | ✅  | Notify if EC2 instances memory breach a certain threshold                                              | Use CloudWatch Agent + CloudWatch Alarm + SNS topic                                                                                                                                     |                          |
| 20  | ✅  | CloudWatch: Publish custom metrics with AWS CLI?                                                       | `aws cloudwatch put-metric-data`                                                                                                                                                        |                          |
| 21  | ❌  | ASG: Scale-out. Newly launched instances are not included in the aggregated metrics. Why?              | (For step scaling), newly launch instance has a warm-up time, before it's counted to aggregated EC2 instance metrics                                                                    | [1.21]                   |
| 22  | ❌  | ASG: Launch 3 instances: 2 in the same AZ. Not error in ASG scaling history. Why?                      | ASG is configured to deploy to 2 AZs.                                                                                                                                                   |                          |
| 23  | ✅  | MySQL + read-intensive. Migrate to AWS + HA + Scalability?                                             | ~~RDS Multi-AZ Cluster + Read replicas~~ -> Aurora + Aurora Auto Scaling (with Aurora Replicas)                                                                                         | [1.23]                   |
| 24  | ✅  | Route53: If primary data center fails, automatically route traffics to secondary?                      | Route53 Failover routing policy                                                                                                                                                         |                          |
| 25  | ✅  | ELB: HA + evenly distributes traffic across targets in all AZs. How?                                   | 1. Launch EC2 across AZs; 2. Config cross-zone load balancing for ELB                                                                                                                   |                          |
| 26  | ✅  | An internal app access via Site-2-Site VPN. Detect any expose & restrict?                              | 1. Create a AWS Config rule to track the SG; 2. Config a System Manager Automation document to remove non-cooperate CIDR-range.                                                         |                          |
| 27  | ✅  | ALB: Spike in `RequestCount` metric. Where to inspect the IP addresses?                                | ELB Access Logs                                                                                                                                                                         |                          |
| 28  | ✅  | Notify - via Slack - AWS service limit                                                                 | AWS Trusted Advisor (Service Limit) + EventBridge rule + Lambda                                                                                                                         |                          |
| 29  | ❌  | KMS: Delete CMK. What happened?                                                                        | When delete a KMS key, AWS KMS requires you to set a waiting period of 7 – 30 days. The default waiting period is 30 days.                                                              | [1.29]                   |
| 30  | ❌  | ALB: 4 EC2 instances, 1: 95%, 3: 10%. Why?                                                             | When scaling up, there is potential for unequal distribution of load due to stickiness -> Manually re-balance the load                                                                  | [1.30]                   |

[1.3]: https://repost.aws/knowledge-center/cloudwatch-push-logs-with-unified-agent
[1.4.1]: https://aws.amazon.com/about-aws/whats-new/2019/01/amazon-cloudwatch-agent-adds-support-for-procstat-plugin-and-multiple-configuration-files/
[1.4.2]: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch-Agent-procstat-process-metrics.html
[1.5.1]: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Dashboards.html
[1.5.2]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html
[1.5.3]: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-cloudwatch-new.html
[1.8]: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/publishingMetrics.html
[1.9]: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Monitoring.OS.html
[1.13]: https://docs.aws.amazon.com/config/latest/developerguide/notifications-for-AWS-Config.html
[1.14]: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/ConsoleAlarms.html
[1.15]: https://aws.amazon.com/premiumsupport/faqs/#AWS_Personal_Health_Dashboard
[1.15.2]: https://docs.aws.amazon.com/health/latest/ug/getting-started-health-dashboard.html
[1.15.3]: https://docs.aws.amazon.com/notifications/latest/userguide/what-is-service.html
[1.17]: https://docs.aws.amazon.com/singlesignon/latest/userguide/manage-your-accounts.html?icmpid=docs_sso_console#assigning-account-access
[1.21]: https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html#as-step-scaling-warmup
[1.23]: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Integrating.AutoScaling.html
[1.29]: https://docs.aws.amazon.com/kms/latest/developerguide/deleting-keys.html
[1.30]: https://docs.aws.amazon.com/elasticloadbalancing/latest/application/sticky-sessions.html

## 1.2 VPC Flow Logs - Logging IP Traffic

### Flow log records

A flow log record represents a network flow in your VPC.

By default, each record captures a network internet protocol (IP) traffic flow (characterized by a 5-tuple on a per network interface basis) that occurs within an aggregation interval, also referred to as a capture window.

Flow log record format:

```
version account-id interface-id
srcaddr dstaddr srcport dstport
protocol packets bytes start end
action log-status
vpc-id subnet-id instance-id tcp-flags type pkt-srcaddr pkt-dstaddr region az-id sublocation-type sublocation-id pkt-src-aws-service pkt-dst-aws-service flow-direction traffic-path
```

An example flow log record for SSH traffic (destination port 22, TCP protocol) to network interface eni-1235b8ca123456789 in account 123456789010 was allowed.

```
2 123456789010 eni-1235b8ca123456789
172.31.16.139 172.31.16.21 20641 22
6 20 4249 1418530010 1418530070
ACCEPT OK
```

An example flow log record for RDP traffic (destination port 3389, TCP protocol) to network interface eni-1235b8ca123456789 in account 123456789010 was rejected.

```
2 123456789010 eni-1235b8ca123456789
172.31.9.69 172.31.9.12 49761 3389
6 20 4249 1418530010 1418530070
REJECT OK
```

## 1.10 ELB Access Logs

### Access log files

ELB publishes a log file for each load balancer node every 5 minutes.

The file name of the access log file has the following format

bucket[/prefix]/`AWSLogs`/aws-account-id/`elasticloadbalancing`/region/yyyy/mm/dd/aws-account-id*`elasticloadbalancing`\_region*`app`.load-balancer-id_end-time_ip-address_random-string`.log.gz`

e.g. `s3://my-bucket/my-prefix/AWSLogs/123456789012/elasticloadbalancing/us-east-2/2022/05/01/123456789012_elasticloadbalancing_us-east-2_app.my-loadbalancer.1234567890abcdef_20220215T2340Z_172.160.001.192_20sg8hgm.log.gz`

### Access log entries

Elastic Load Balancing logs requests sent to the load balancer, including requests that never made it to the targets.

Each log entry contains the details of a single request (or connection in the case of WebSockets) made to the load balancer.

All fields of a log entry are delimited by spaces.

The format of an access log entries:

```
type time elb
client:port target:port request_processing_time target_processing_time response_processing_time elb_status_code target_status_code received_bytes sent_bytes
"request" "user_agent" ssl_cipher ssl_protocol
target_group_arn
"trace_id" "domain_name" "chosen_cert_arn"
matched_rule_priority request_creation_time "actions_executed" "redirect_url" "error_reason" "target:port_list" "target_status_code_list" "classification"
```

An example log entry for an HTTPS listener (port 443 to port 80):

```
https 2018-07-02T22:23:00.186641Z app/my-loadbalancer/50dc6c495c0c9188
192.168.131.39:2817 10.0.0.1:80 0.086 0.048 0.037 200 200 0 57
"GET https://www.example.com:443/ HTTP/1.1" "curl/7.46.0" ECDHE-RSA-AES128-GCM-SHA256 TLSv1.2
arn:aws:elasticloadbalancing:us-east-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067
"Root=1-58337281-1d84f3d73c47ec4e58577259" "www.example.com" "arn:aws:acm:us-east-2:123456789012:certificate/12345678-1234-1234-1234-123456789012"
1 2018-07-02T22:22:48.364000Z "authenticate,forward" "-" "-" "10.0.0.1:80" "200" "-" "-"
```

[1.10]: https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-access-logs.html

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
