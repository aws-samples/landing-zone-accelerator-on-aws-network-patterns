# Landing Zone Accelerator on AWS - Sample Network Patterns - Hub and Spoke

## Overview
This sample configuration demonstrates how to create a centralized inspection VPC using AWS Landing Zone Accelerator. It sets up a centralized Ingress VPC, centralized Egress VPC, and centralized Inspection VPC leveraging Gateway Load Balancer Endpoints.  

This yaml template can be used as a starting point for developing a centralized inspection architecture with AWS LZA.

# Configuration Summary
This file serves to provide a general overall summary of the LZA configuration files.

1. Centralized VPC Service Endpoints are deployed in Network account
2. All public ingress traffic flows in from Ingress VPC and is sent to Inspection VPC prior to being sent to workload VPC (ex. Application Load Balancers or F5s can be hosted in Ingress VPC, with targets in workload VPCs)
3. Public Subnets are deployed in Workload VPCs in this template, but can be removed with above model.
4. All egress traffic to Internet from Workload VPCs flows thru Inspection VPC (GWLB endpoints) and is then sent to centralized Egress VPC NAT Gateways.

> **_Note_:** LZA administrators are required to review all configuration files and adjust to fit organizational security and compliance needs. This configuration does not inheritly provide full compliance for any framework. Visit the [configuration reference](https://awslabs.github.io/landing-zone-accelerator-on-aws/) to explore available customizations for LZA.
> 
## Architecture Diagram
1. Refer to the [Best Practices](https://aws.amazon.com/blogs/networking-and-content-delivery/centralized-inspection-architecture-with-aws-gateway-load-balancer-and-aws-transit-gateway/) for Gateway Load Balancer centralized inspection patterns.

### __Network Configuration__
| Configuration Item | Status | Detail |
| - | - | - |
| Delete Default VPC | Disalbed |  |
| Central IPAM | Enabled | /16 Defined for Home Region |
| VPC Endpoint Policies | Defined | Default and EC2 VPC endpoints |
| Provisioned VPCs | Defined | Workload, Ingress, Egress, Inspection, Shared-Services |
| Global VPC Flow Logs | Enabled | Delivery to CloudWatch Logs |

### __Accounts Configuration__
This sample has minimal dependency on this config file. It only defines the additional example application accounts for demonstrative purposes.
|  Configuration Item | Status | Detail |
| - | - | - |
| Workload AWS Accounts | Defined | SharedServices <br> Network <br> App-1 <br> App-2 |

### __Organization Configuration__
This sample has minimal dependency on this config file. It only adds the additional OUs for demonstrative purposes.
| Configuration Item | Status | Detail 
| - | - | - |
| OUs | Defined | Workload <br> Infrastructure |


# For further consideration
This is a baseline for Landing Zone Accelerate which demonstrates how to deploy a centralized ingress, egress, and inspection VPC. It is a _starting point_ for you to use, as you align your organization objectives and tailor to your specific business requirements. AWS provides resources for you to consult with, as you begin customizing your deployment of LZA:

1. Refer to the [Best Practices](https://aws.amazon.com/blogs/mt/best-practices-for-organizational-units-with-aws-organizations/) for Organizational Units with AWS Organizations blog post for an overview.
1. Refer to the [Best Practices](https://aws.amazon.com/blogs/networking-and-content-delivery/centralized-inspection-architecture-with-aws-gateway-load-balancer-and-aws-transit-gateway/) for Gateway Load Balancer centralized inspection patterns.
1. [Recommended OUs and accounts](https://docs.aws.amazon.com/whitepapers/latest/organizing-your-aws-environment/recommended-ous-and-accounts.html). This section of the `Organizing your AWS Environment Using Multiple` Accounts Whitepaper discusses the deployment of specific-purpose OUs in addition to the foundational ones established by the LZA. For example, you may wish to establish a `Sandbox` OU for experimentation, a `Policy Staging` OU to safely test policy changes before deploying them more broadly, or a `Suspended` OU to hold, constrain, and eventually retire accounts that you no longer need.
1. [AWS Security Reference Architecture (SRA)](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/welcome.html). The SRA "is a holistic set of guidelines for deploying the full complement of AWS security services in a multi-account environment." This document helps you to explore the "big picture" of AWS security and security-related services in order to determine the architectures most suited to your organization's unique security requirements.
1. LZA on AWS [Implementation Guide](https://docs.aws.amazon.com/solutions/latest/landing-zone-accelerator-on-aws/solution-overview.html). This is the official documentation of the Landing Zone Accelerator Project and serves as your starting point. Use the instructions in the implementation guide to stand up your environment.
1. AWS Labs [LZA Accelerator](https://github.com/awslabs/landing-zone-accelerator-on-aws) GitHub Repository. This is the official codebase of the Landing Zone Accelerator Project.
