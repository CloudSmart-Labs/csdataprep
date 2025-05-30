![CloudSmart Logo](https://user-images.githubusercontent.com/26460009/182591500-ac99b0d8-2639-4a28-8357-97d09e0e2063.png)
# CloudSmart Insights Data Prep Workshop for AWS Marketplace

## Introduction
CloudSmart Insights helps AWS Marketplace sellers gain valuable insights into their sales activities. This data preparation workshop guides you through setting up the necessary components to access CloudSmart Insights, with a focus on embedding security guardrails and implementing least privilege access to your data.

The workshop consists of three main labs that will help you:
1. Create an AWS Marketplace listing
2. Integrate with AWS Marketplace APIs
3. Set up the CloudSmart Data Collector for analytics

![CloudSmart Badge](https://user-images.githubusercontent.com/26460009/183915211-2252735e-bf8f-4ffa-b619-c14e4ae59436.png)

## Workshop Navigation
- [Prerequisites for AWS Marketplace Sellers](/docs/MarketplacePrerequisite.md)
- [Workshop 1: List a SaaS Subscription](/docs/Lab1.md)
- [Workshop 2: Use the AWS Marketplace Integration SaaS](/docs/Lab2.md)
- [Workshop 3: CloudSmart Data Collector](/docs/Lab3.md)

## Prerequisites
Before starting this workshop, you'll need:

1. **An AWS Account** with appropriate permissions
   - Basic knowledge of AWS services like IAM and S3 is recommended
   - You must be registered as a seller in AWS Marketplace

2. **AWS Marketplace Seller Account**
   - Access to the AWS Marketplace Management Portal
   - Appropriate IAM permissions to create and manage AWS Marketplace listings

3. **Data Feed Configuration**
   - You'll need to specify a target location in the AWS Marketplace Management Portal
   - This workshop will guide you through the [Data Feed Configuration](https://aws.amazon.com/marketplace/management/reports/data-feed-configuration) process

## Workshop Structure

### [Workshop 1: List a SaaS Subscription](/docs/Lab1.md)
Learn how to create a SaaS Subscription listing in AWS Marketplace. This lab guides you through the process of setting up your product listing with the appropriate pricing model and configuration.

### [Workshop 2: Use the AWS Marketplace Integration SaaS](/docs/Lab2.md)
Set up the AWS Marketplace Integration SaaS to handle customer subscriptions, entitlements, and metering. This lab shows you how to deploy and configure the necessary components to integrate with AWS Marketplace APIs.

### [Workshop 3: CloudSmart Data Collector](/docs/Lab3.md)
Configure the CloudSmart Data Collector to access your AWS Marketplace data and visualize it in the CloudSmart Insights dashboard. This lab guides you through setting up secure data transfer between your AWS account and CloudSmart.

## Additional Resources
Credit to the AWS Marketplace teams that made this possible. Please see the following links for additional information:
- [AWS Marketplace SaaS Quick Start](https://aws-ia.github.io/cloudformation-aws-marketplace-saas/)
- [AWS Marketplace Seller Registration Process](https://docs.aws.amazon.com/marketplace/latest/userguide/seller-registration-process.html)
- [AWS Marketplace ISV Samples](https://github.com/aws-samples/aws-marketplace-isv-samples)

## License
This library is licensed under the MIT-0 License. See the LICENSE file for details.
