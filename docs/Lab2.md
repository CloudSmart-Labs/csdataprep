![CloudSmart Logo](https://user-images.githubusercontent.com/26460009/182591613-37eaf99b-9c58-444c-94c2-8f6fb229f26d.png)
# CloudSmart Insights Data Prep Workshop for AWS Marketplace

## Workshop 2: Use the AWS Marketplace Integration SaaS

### Navigation
- [Prerequisites for AWS Marketplace Sellers](/docs/MarketplacePrerequisite.md)
- [Workshop 1: List a SaaS Subscription](/docs/Lab1.md)
- [Workshop 2: Use the AWS Marketplace Integration SaaS (Current)](/docs/Lab2.md)
- [Workshop 3: CloudSmart Data Collector](/docs/Lab3.md)

## Introduction
With software as a service (SaaS) products, you deploy and manage software in your AWS account and grant buyers access to the application. You are responsible for managing customer access, account creation, resource provisioning, and account management within your software.

## Workshop Overview
AWS Marketplace offers an AWS Partner Solution to streamline the integration of SaaS products with AWS Marketplace. In this lab, you will set up this solution for the product that you have created in the [Lab 1: Create a SaaS listing](/docs/Lab1.md).

### Tasks
1. Deploy the Serverless SaaS Integration AWS Partner solution
2. Confirm the Amazon SNS subscription
3. Update your product with the new registration page URL
4. Modify and upload your registration page
5. Simulate the buyer experience
6. Check entitlement and add metering records

![Tasks Overview](https://github.com/tvanceadv/csdataprep/assets/26460009/0b08fd1f-20d3-4905-8755-2528c788a144)

The solution is a lightweight serverless implementation that provides the core capabilities required to integrate your SaaS solution with its corresponding listing in AWS Marketplace. The solution's capabilities include accepting new customer registrations, granting and revoking customer access, updating customer entitlements, and reporting metered usage. For more information, see [AWS Marketplace Serverless SaaS Integration on AWS](https://aws.amazon.com/solutions/implementations/aws-marketplace-saas/).

![Architecture Diagram](https://github.com/tvanceadv/csdataprep/assets/26460009/58a8b9d7-c836-430f-817a-147c5fb34edf)

## Prerequisites
- **A limited listing SaaS product** - If you do not have a product staged in limited in AWS Marketplace yet, complete the [Workshop 1: List a SaaS Subscription](/docs/Lab1.md) to create one. A product staged in limited is only accessible from the seller account or allowlisted test accounts.
- **Your product details** - These details include your product code and [Amazon Simple Notification Service (SNS)](https://aws.amazon.com/sns/) topics for your product.
- **An email ID** - An email (distribution list) to receive notifications every time someone subscribes to your product.
- **Required IAM permissions** - You must have various IAM permissions in your AWS account, including CloudFormation, IAM, Lambda, CloudFront, SNS, SQS, DynamoDB, EventBridge, S3, API Gateway, CloudShell, and AWS Marketplace permissions.

> **Note**: For detailed instructions on completing this workshop, please refer to the original AWS Marketplace documentation. This page provides a simplified overview of the process.

## Next Steps
After completing this workshop, continue to [Workshop 3: CloudSmart Data Collector](/docs/Lab3.md) to set up the CloudSmart Data Collector for accessing your AWS Marketplace data.

---

[Return to Workshop Index](/docs/index.md)