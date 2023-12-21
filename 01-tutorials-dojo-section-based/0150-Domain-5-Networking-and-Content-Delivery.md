# Tutorial Dojo - SOA-C02 - Domain 5: Networking and Content Delivery

| No  |     | Q                                                                                                                         | A                                                                                                                                                                                 | Ref                                                            |
| --- | --- | ------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
|     |     |                                                                                                                           |                                                                                                                                                                                   |                                                                |
| 1   | ✅  | Migrate to IPv6. Ensure app can initiate outgoing traffic, but blocks any incoming connection from internet.              | [Outbound-only internet communication](#51-outbound-only-internet-communication)                                                                                                  | [^5.1.1] [^5.1.2]                                              |
| 2   | ✅  | Dedicate connection between on-premise and AWS. Which service?                                                            | AWS Direct Connect                                                                                                                                                                |                                                                |
| 3   | ✅  | ASG, EC2, ALB. Allow HTTP/s not working. NACL, SG?                                                                        | NACL: allows inbound 80, 443; outbound: **ephemeral ports**[^5.3.1][^5.3.2] (1024-65535); SG: allows inbound (80, 443) (outbound is implicitly include with inbound)              |                                                                |
| 4   | ✅  | Route 53: 2 AWS regions. Route to nearest region?                                                                         | Route 53 Geo-proximity (Compliance > Fastest (low latency))                                                                                                                       |                                                                |
| 5   | ❌  | Site-2-Site VPN. How to config route table?                                                                               | Target GW: RT points to CGW. CGW: RT points to Target GW                                                                                                                          |                                                                |
| 6   | ✅  | EC2 (private subnet): not allow connection initiated from the internet? HA.                                               | Use a `NAT Gateway` (in public subnet) (not ~~NAT instance~~)                                                                                                                     |                                                                |
| 7   | ✅  | VPC: Connect to internet & on-premises?                                                                                   | Internet Gateway[^5.7.1] + Virtual Private Gateway (for Site-2-Site VPN)                                                                                                          |                                                                |
| 8   | ❌  | VPC: Public subnet, SG, IGW. Config?                                                                                      | [Public subnet](#58-config-route-table-for-public--private-subnet)                                                                                                                |                                                                |
| 9   | ✅  | 3 VPCs. Ensure EC2 instances in all VPCs can communicate with each other?                                                 | 1. 3 VPCs peered together[^5.9.1]: Use VPC Peering + Route traffic to each other ("full mesh") + IP not overlap; 2. Use Transit Gateway[^5.9.2]                                   |                                                                |
| 10  | ✅  | Internal app inside a VPC, allocate a custom domain name for the database. How?                                           | Use Route 53 **Private Hosted Zone**: Create a A/AAAA record                                                                                                                      |                                                                |
| 11  | ✅  | VPC: 2 subnet A & B with 2 EC2 instances EC2-A & EC2-B. Logged in instance EC2-A. Can react a HTTP port, but cannot ping? | 1. Outbound rule of NACL A deny ICMP; 2. Inbound rule of NACL-A/SG-A not allow ICMP.                                                                                              | VPC subnet **NACL**[^5.11.1] <br> EC2 **SG**[^5.11.2]          |
| 12  | ✅  | Block traffic from an IP address. How?                                                                                    | VPC subnet NACL: Add inbound rule that deny traffic from that IP (/32)                                                                                                            |                                                                |
| 13  | ✅  | Custom VPN: NACL, SG allow port 80, 443. But clients still cannot access via HTTP/s?                                      | Outbound traffic to client's not allowed yet. VPC subnet NACL: Add an outbound rule allow traffic to ephemeral ports (Same as 5.1)                                                |                                                                |
| 14  | ❌  | Route 53 routes traffics to multiple ELB in different regions. How to config?                                             | [DNS failover in complex configs]                                                                                                                                                 | [^5.14] [^5.14.2]                                              |
| 15  | ✅  | Local machine: Ping to EC2 instance: Fail: Why?                                                                           | Enable Flow Logs: Check the traffic logs: Allow inbound/outbound traffic for the EC2 instance.                                                                                    |                                                                |
| 16  | ✅  | VPC with servers in private subnets and NAT                                                                               |                                                                                                                                                                                   | [^5.16]                                                        |
| 17  | ✅  | New version: Test before move all traffic: Which Route 53 routing policy?                                                 | Route 53 weighted routing policy                                                                                                                                                  |                                                                |
| 18  | ✅  | 2 servers (2 EC2 instances): Route traffics to A if 2xx, 3xx HTTP, otherwise to B.                                        | Active-passive failover[^5.18.1] (primary + standby). EC2 (can't not create alias record) -> Create a normal record with HTTP health check[^5.18.2]                               |                                                                |
| 19  | ✅  | VPC: Public subnet + VGW + NAT instance: Route table of VPC                                                               | 1. VPC CIDR -> local; 2. VPN CIDR -> VGW; 3. All (remaining) traffic -> NAT instance                                                                                              | VPC route table [^5.19] <br> VPC route table options [^5.19.2] |
| 20  | ✅  | Push update for app: User around the worlds: Easiest & Best UX?                                                           | S3 + CloudFront                                                                                                                                                                   |                                                                |
| 21  | ✅  | NACL: Application cannot response to clients. SG: Client cannot access app (on EC2). Why?                                 | NACL: Need both inbound rule (well-known ports 80, 443, 22) & outbound rule (ephemeral ports) for traffics. SG: Explicitly allow **request** traffic from all clients (0.0.0.0/0) |                                                                |
| 22  | ✅  | Serverless video-on-demand workflow. Architecture?                                                                        | S3 -> Lambda -> AWS Elemental MediaConvert -> S3 -> CloudFront                                                                                                                    | [^5.22]                                                        |
| 23  | ✅  | EC2: IPv4 + Download security patch from internet, but block traffic initiate from internet. How?                         | Use NAT Gateway / NAT instance                                                                                                                                                    |                                                                |
| 24  | ✅  | EC2: SSH. Failed. Why?                                                                                                    | 1. VPC: IGW <- RT; 2. Subnet: NACL; 3. EC2: Instance: SG + Public IP + Running (pass health check)?                                                                               | [^5.24]                                                        |
| 25  | ✅  | 2 EC2 instance: Communicate with each other, but not the internet.                                                        | 1. Private subnet (same region); 2. Same SG.                                                                                                                                      |                                                                |
| 26  | ✅  | Private connection between on-premise & AWS (without using public internet). Which service?                               | Direct Connect (not Site-2-Site VPN <- Use public internet)                                                                                                                       |                                                                |
| 27  | ✅  | EC2 in private subnet: Connect to S3: How?                                                                                | Use VPC endpoint ()                                                                                                                                                               |                                                                |
| 28  | ✅  | VPC subnet NACL: Inbound: `100 - ALL - DENY`; `105 - 80 - ALL`; `* - ALL - DENY`. What will happen?                       | All inbound traffic will be denied <- Rules are evaluated starting with the lowest numbered rule, NACL stop when a rule match traffic.                                            | [^5.28]                                                        |
| 29  | ✅  | VPC: EC2 instances don't have a public DNS hostname -> cannot access the instance from the internet. Why?                 | VPC DNS attributes[^5.29.2]: `enableDnsSupport` (default: on); `enableDnsHostnames` (default: off) -> Instance isn't assigned a _public_ DNS hostname                             | [^5.29]                                                        |
| 30  | ✅  | VPC: EC2 + RDS: EC2 cannot connect RDS. Why?                                                                              | By default, network access is turned off for a DB instance; You need to explicitly allow access to DB instance with SG inbound rule, e.g. port 3306 (MySQL), port 22 (SSH)        | [^5.30]                                                        |

## 5.1 Outbound-only internet communication

To enable outbound-only internet communication:

- Over IPv4: use a **`NAT Gateway`** + `IGW`[^5.1.3]

- Over IPv6: use **`egress-only internet gateway`**[^5.1.4]

  IPv6 addresses are globally unique, and are therefore public by default. To enable outbound-only internet communication, we need to "make it private" with `egress-only internet gateway`.

[^5.1.1]: <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-migrate-ipv6.html>
[^5.1.2]: <https://docs.aws.amazon.com/vpc/latest/userguide/egress-only-internet-gateway.html>
[^5.1.3]: <https://docs.aws.amazon.com/vpc/latest/userguide/nat-gateway-scenarios.html#public-nat-internet-access>
[^5.1.4]: <https://docs.aws.amazon.com/vpc/latest/userguide/egress-only-internet-gateway.html>

## 5.7 Connect to internet using an internet gateway

> [!NOTE]
> What is an internet gateway?
>
> A horizontally scaled, redundant, and highly available **VPC component** that _allows communication_ between your VPC & the **internet**.

> [!NOTE]
> What does an internet gateway do?
>
> An internet gateway allows:
>
> - resources in your _public_ subnets (e.g. EC2 instances) to connect to the internet if the resource has a public IPv4 address or an IPv6 address
> - resources on the internet can initiate a connection to resources in your (public) subnet using the public IPv4 address or IPv6 address

> [!NOTE]
> How does internet gateway work?
>
> An internet gateway provides a target in your VPC route tables for internet-routable traffic.
>
> - For communication using IPv4, the internet gateway also performs network address translation (NAT).
> - For communication using IPv6, NAT is not needed because IPv6 addresses are public

## 5.8 Config Route Table for Public & Private subnet

## 5.14 DNS failover in complex configs

Example:

1. Select a region close to a user (👈 Use latency `alias records` & set the value of `Evaluate Target Health` to Yes)

   > [!NOTE]
   > By setting the value of `Evaluate Target Health` to `Yes`, Route 53 will determine whether there are any healthy resources in a region before trying to route traffic there.[^5.14]
   >
   > If not, Route 53 chooses a healthy resource in the other region.

2. Select a resource in that region
   1. Use weighted records for two or more resources within each region to protect against the failure of a single endpoint or an AZ
   2. Use a ELB

[^5.3.1]: <https://www.wikiwand.com/en/Ephemeral_port>
[^5.3.2]: <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html#nacl-ephemeral-ports>
[^5.7.1]: <https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html>
[^5.9.1]: <https://docs.aws.amazon.com/vpc/latest/peering/peering-configurations-full-access.html#three-vpcs-full-access>
[^5.9.2]: <https://docs.aws.amazon.com/vpc/latest/tgw/how-transit-gateways-work.html#architecture-diagram>
[^5.11.1]: <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html>
[^5.11.2]: <https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2-security-groups.html>
[^5.14]: <https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-complex-configs.html>
[^5.14.2]: <https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/health-checks-how-route-53-chooses-records.html>
[^5.16]: <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-example-private-subnets-nat.html>
[^5.18.1]: <https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-types.html#dns-failover-types-active-passive>
[^5.18.2]: <https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-simple-configs.html>
[^5.19]: <https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html>
[^5.19.2]: <https://docs.aws.amazon.com/vpc/latest/userguide/route-table-options.html>
[^5.22]: <https://aws.amazon.com/mediaconvert/>
[^5.24]: <https://repost.aws/knowledge-center/instance-vpc-troubleshoot>
[^5.28]: <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html#nacl-rules>
[^5.29]: <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-dns.html>
[^5.29.2]: <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-dns.html#vpc-dns-support>
[^5.30]: <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.RDSSecurityGroups.html>
