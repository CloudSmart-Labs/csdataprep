![CloudSmart Logo](https://user-images.githubusercontent.com/26460009/182591500-ac99b0d8-2639-4a28-8357-97d09e0e2063.png)
# CloudSmart Insights Data Prep Workshop for AWS Marketplace

## Workshop 3: CloudSmart Data Collector to Access the Dashboard

### Navigation
- [Prerequisites for AWS Marketplace Sellers](/docs/MarketplacePrerequisite.md)
- [Workshop 1: List a SaaS Subscription](/docs/Lab1.md)
- [Workshop 2: Use the AWS Marketplace Integration SaaS](/docs/Lab2.md)
- [Workshop 3: CloudSmart Data Collector (Current)](/docs/Lab3.md)

### Introduction
CloudSmart Insights onboarding occurs in two parts:
1. Creation of the CloudSmart SaaS tenant, which permits the data collector to aggregate the Marketplace data
2. Creation of tenant resources to copy data

![CloudSmart Badge](https://user-images.githubusercontent.com/26460009/183915211-2252735e-bf8f-4ffa-b619-c14e4ae59436.png)

### Prerequisites
- Completed [Workshop 1](/docs/Lab1.md) and [Workshop 2](/docs/Lab2.md)
- Access to your AWS Marketplace seller account
- AWS account credentials with permissions to create CloudFormation stacks

### Step 1: Prepare Required Information
Before launching the CloudFormation template, gather the following information:

- **Source Account ID**: Your AWS Account ID (12 digits)
- **Root Folder Name**: The digits from the Tenant name created in the SaaS application
- **Suffix**: A unique identifier to prevent bucket name conflicts
- **Destination Account ID**: Set to 044080027516 (CloudSmart's account)

### Step 2: Launch the CloudFormation Stack
Choose the appropriate stack based on your enrollment status:

- **For New Enrollment to AWS Marketplace SDDS**:  
  [Launch CloudSmart Data Collector](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create?&templateURL=https%3A%2F%2Ftenant-template.s3.amazonaws.com%2FFinalTemplate.yml)

- **For Existing Enrollment to AWS Marketplace SDDS**:  
  [Launch CloudSmart Data Collector for Existing SDDS Users](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create?&templateURL=https%3A%2F%2Ftenant-template.s3.amazonaws.com%2FFinalTemplateV2.yml)

### Step 3: Configure the CloudFormation Stack
1. Enter a Stack Name (e.g., CSMPDataFeed)
2. Enter the Root Folder Name (assigned by CloudSmart)
3. Enter your Source Account ID (12-digit AWS Account number)
4. Enter a unique Suffix to prevent bucket naming conflicts

![CloudFormation Stack Configuration](https://github.com/tvanceadv/csdataprep/assets/26460009/d12f0042-6aa5-4b81-9e7c-c577f92a8599)

### Step 4: Review and Create the Stack
1. Review the configuration parameters
2. Acknowledge the IAM resource creation
3. Click Create Stack

![CloudFormation Stack Creation](https://github.com/tvanceadv/csdataprep/assets/26460009/7d534e73-9e96-4881-8eb0-66b40caeaaa3)

### Step 5: Note the CloudFormation Outputs
After the stack creation completes, note the following outputs:
- S3 Bucket URL
- KMS Key ARN
- KMS Key ID
- Lambda Role ARN

![CloudFormation Stack Outputs](https://github.com/tvanceadv/csdataprep/assets/26460009/a9a266cf-04f9-4a42-8c3c-0f86546c0da5)

### Step 6: Configure AWS Marketplace Data Feed
1. Navigate to the [AWS Marketplace Data Feed Configuration](https://aws.amazon.com/marketplace/management/reports/data-feed-configuration) page
2. Enter the Amazon Resource Names (ARNs) from the CloudFormation outputs:
   - S3 Bucket ARN
   - KMS Key ARN
   - Optional: SNS Topic ARN (if configured)
3. Click Submit

![AWS Marketplace Data Feed Configuration](https://github.com/tvanceadv/csdataprep/assets/26460009/510834a5-7883-486a-8122-3e3bed2d0e1b)

### Resources Created by the Template
The CloudFormation template deploys the following resources:
- S3 Bucket (for storing AWS Marketplace data)
- Bucket Policy (for secure access)
- KMS Key (for encryption)
- KMS Key Alias
- Lambda Function (establishes the sync between CloudSmart's bucket and your bucket)
- Lambda Function Role
- Lambda Invoke Permission
- Custom Resources: Lambda Function Trigger (adding the S3 bucket notification)

### How It Works
The template deploys an S3 bucket encrypted with a KMS key in your AWS Marketplace Account. When AWS Marketplace sends new data to your bucket, it gets securely synchronized to CloudSmart's system for analysis.

> **Note**: After the stack is deployed in your AWS account, CloudSmart will need the Lambda Role ARN to complete the bucket synchronization setup.

### Completion
Once the data feed is configured, you are ready to use the CloudSmart Insights tool to manage your AWS Marketplace go-to-market strategy. You'll be able to access your data through the CloudSmart Insights dashboard.

![CloudSmart Insights Dashboard](https://github.com/tvanceadv/csdataprep/assets/26460009/11ab6ada-f9a2-4804-896b-dd93d68e8c38)

### Support
If you encounter any issues during this process, please contact CloudSmart support for assistance.

---

[Return to Workshop Index](/docs/index.md)
