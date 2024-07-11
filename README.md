# Landing Zone Accelerator on AWS  - Sample Network Patterns

## Overview
The [Landing Zone Accelerator on AWS](https://aws.amazon.com/solutions/implementations/landing-zone-accelerator-on-aws/) (LZA) is architected to align with AWS best practices and in conformance with multiple, global compliance frameworks. We recommend customers deploy AWS Control Tower as the foundational landing zone and enhance their landing zone capabilities with Landing Zone Accelerator. These complementary capabilities provides a comprehensive no-code solution across 35+ AWS services to manage and govern a multi-account environment built to support customers with highly-regulated workloads and complex compliance requirements. AWS Control Tower and Landing Zone Accelerator help you establish platform readiness with security, compliance, and operational capabilities.

Landing Zone Accelerator is provided as an open-source project that is built using the AWS Cloud Development Kit (CDK). You install directly into your environment to get full access to the infrastructure as code (IaC) solution. Through a simplified set of configuration files, you are able to configure additional functionality, controls and security services (eg. AWS Managed Config Rules, and AWS Security Hub), manage your foundational networking topology (eg. VPCs, Transit Gateways, and Network Firewall), and generate additional workload accounts using the AWS Control Tower Account Factory.

There are no additional charges or upfront commitments required to use Landing Zone Accelerator on AWS. You pay only for AWS services enabled in order to set up your platform and operate your controls. This solution can also support non-standard AWS partitions, including AWS GovCloud (US), and the US Secret and Top Secret regions.

For an overview and solution deployment guide, please visit [Landing Zone Accelerator on AWS](https://aws.amazon.com/solutions/implementations/landing-zone-accelerator-on-aws/)

## Deployment
These configuration files are a complete set extending our sample best practices. Minimal alterations are required for these configs to deploy a demo environment show-casing various network designs. However, they will need modification to align with your organizations requirements for a production deployment.

1. **Deploy the Landing Zone Accelerator on AWS solution**. To deploy the LZA, please visit the [Deployment Process Overview](https://docs.aws.amazon.com/solutions/latest/landing-zone-accelerator-on-aws/deployment-overview.html)
1. **Apply the sample network patterns**. To apply a sample configuration, choose a set of configs from one of the subfolders. Then see our instructions to [Update the configuration files](https://docs.aws.amazon.com/solutions/latest/landing-zone-accelerator-on-aws/step-3.-update-the-configuration-files.html). 

alert:: These configs have been tested on v1.6.0 of the Landing Zone Accelerator

## Important
These assets aren't intended to be feature complete or fully compliant, but rather to help accelerate cloud migrations and cloud refactoring efforts by entities required to meet region- or industry-specific security requirements. While these assets can help you reduce the effort required to manually build a production-ready infrastructure, you will still need to tailor them to your unique business needs. For more information about how to use AWS in compliance with specific requirements, see [AWS Compliance Programs](https://aws.amazon.com/compliance/programs/). Consult with your AWS team to understand controls to meet your requirements.

For more information on how to manage your configuration files please see [Configuration File Best Practices](https://docs.aws.amazon.com/solutions/latest/landing-zone-accelerator-on-aws/configuration-file-best-practices.html)

## References
* LZA on AWS [Implementation Guide](https://docs.aws.amazon.com/solutions/latest/landing-zone-accelerator-on-aws/landing-zone-accelerator-on-aws.pdf). This is the official documentation of the Landing Zone Accelerator Project and serves as your starting point. Use the instructions in the implementation guide to stand up your environment.
* AWS Labs [LZA Accelerator](https://github.com/awslabs/landing-zone-accelerator-on-aws) GitHub Repository. This is the official codebase of the Landing Zone Accelerator Project.