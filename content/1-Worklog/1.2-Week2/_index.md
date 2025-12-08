---
title: "Week 2 Worklog"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---



### Week 2 Objectives:

* Deploy and manage Amazon EC2 instances within VPC environment.
* Set up hybrid DNS with Route 53 Resolver.
* Deploy Microsoft AD and configure DNS endpoints.
* Practice VPC Peering to connect multiple VPCs.
* Set up AWS Transit Gateway for multi-VPC connectivity.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Deploy Amazon EC2 Instances: <br>&emsp; + Create EC2 server <br>&emsp; + Test connectivity <br>&emsp; + Create NAT Gateway <br>&emsp; + Use Reachability Analyzer <br>&emsp; + Create EC2 Instance Connect Endpoint <br>&emsp; + AWS Systems Manager Session Manager <br>&emsp; + CloudWatch Monitoring & Alerting                                                                                                   | 15/09/2025 | 15/09/2025      | [Getting started with Amazon VPC and AWS Site-to-Site VPN](https://000003.awsstudygroup.com/vi/) |
| 3   | - Set up hybrid DNS with Route 53 Resolver: <br>&emsp; + Create key pair <br>&emsp; + Initialize CloudFormation Template <br>&emsp; + Configure security group                                              | 16/09/2025 | 16/09/2025      | [Set up hybrid DNS with Route 53 Resolver](https://000010.awsstudygroup.com/vi/) |
| 4   | - Connect RDGW <br> - Deploy Microsoft AD <br>&emsp; - Set up DNS: <br>&emsp; + Create Route 53 Outbound Endpoint <br>&emsp; + Create Route 53 Resolver Rules <br>&emsp; + Test results <br>&emsp; + Create Route 53 Inbound Endpoints | 17/09/2025 | 17/09/2025      | [Set up hybrid DNS with Route 53 Resolver](https://000010.awsstudygroup.com/vi/) |
| 5   | - Set up VPC peering: <br>&emsp; + Initialize CloudFormation Template <br>&emsp; + Create Security Group <br>&emsp; + Create EC2 instance <br>&emsp; + Update Network ACL <br>&emsp; + Create Peering connection <br> - Enable Cross-Peer DNS                            | 18/09/2025 | 18/09/2025      | [Set up VPC Peering](https://000019.awsstudygroup.com/vi/) |
| 6   | - Set up AWS Transit Gateway <br>&emsp; + Create Key Pair <br>&emsp; + Initialize CloudFormation Template <br>&emsp; + Create Transit Gateway <br>&emsp; + Create Transit Gateway Attachments <br>&emsp; + Create Transit Gateway Route Tables <br>&emsp; + Add Transit Gateway Routes to VPC Route Tables                                                                                     | 19/09/2025 | 19/09/2025      | [Set up AWS Transit Gateway](https://000020.awsstudygroup.com/vi/) |


### Week 2 Achievements:

* **Successfully deployed Amazon EC2 Instances:**
  * Created and configured EC2 servers within VPC
  * Tested connectivity and troubleshot network issues
  * Created NAT Gateway for outbound internet access
  * Used Reachability Analyzer to analyze connectivity
  * Set up EC2 Instance Connect Endpoint
  * Configured AWS Systems Manager Session Manager
  * Set up CloudWatch Monitoring & Alerting

* **Set up Hybrid DNS with Route 53 Resolver:**
  * Created key pair for security
  * Initialized and deployed CloudFormation Template
  * Configured security group for DNS traffic
  * Understood how DNS resolution works in hybrid environment

* **Deployed Microsoft AD and DNS Configuration:**
  * Connected RDGW (Remote Desktop Gateway)
  * Deployed Microsoft Active Directory
  * Created Route 53 Outbound Endpoint
  * Configured Route 53 Resolver Rules
  * Created Route 53 Inbound Endpoints
  * Tested and verified DNS resolution results

* **Practiced VPC Peering:**
  * Initialized CloudFormation Template for multi-VPC setup
  * Created Security Group for cross-VPC communication
  * Created EC2 instance in different VPCs
  * Updated Network ACL for peering traffic
  * Created VPC Peering connection
  * Enabled Cross-Peer DNS resolution

* **Set up AWS Transit Gateway:**
  * Created Key Pair for EC2 instances
  * Deployed CloudFormation Template for Transit Gateway
  * Created and configured Transit Gateway
  * Set up Transit Gateway Attachments
  * Created Transit Gateway Route Tables
  * Added Transit Gateway Routes to VPC Route Tables
  * Understood how Transit Gateway works as a central hub
