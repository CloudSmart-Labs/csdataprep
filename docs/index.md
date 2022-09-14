![FullColor250](https://user-images.githubusercontent.com/26460009/182591500-ac99b0d8-2639-4a28-8357-97d09e0e2063.png)
# CloudSmart Data Prep Workshop for AWS Marketplace

Customer Data Prep Workshop for CloudSmart LLC

## Introduction
CloudSmart customers are sellers within the AWS Marketplace and are looking for insights into their sales activities.  Our goal in this data prep workshop is to embed the guardrails and principle of least privilege access to any data.  Ultimately the data prep workshop will be consumed by the CloudSmart Commerce Engine to provide meaningful sales analytics, reporting, and connectivity to customers.

![CloudSmartBadge](https://user-images.githubusercontent.com/26460009/183915211-2252735e-bf8f-4ffa-b619-c14e4ae59436.png)

## Pre-requisites
An AWS Account is required. Basic knowledge of AWS foundational services such as Identity and Access Management (IAM) and Amazon S3 are strongly encouraged.  Given that this dataset is based on the AWS Marketplace, being a seller in the AWS Marketplace is also required. Access to the AWS Account associated with the marketplace management portal and appropriate IAM permissions are also necessary. see https://docs.aws.amazon.com/marketplace/latest/userguide/seller-registration-process.html

Before getting started with the workshop, you need to follow these preparation steps. The workshop is designed with a "bring your own data" mindset, these instructions are here to help you prepare your own dataset.

## Additional Pre-requisite for AWS Marketplace Sellers
You must have appropriate IAM and account permission to access the AWS Marketplace Management Portal. To configure your seller storage configuration, you need to specify a target location in the AWS Marketplace Management Portal. https://aws.amazon.com/marketplace/management/reports/data-feed-configuration

## Setting up the environment
AWS Marketplace Sellers and the AWS Marketplace Sales data are located within US-EAST-1 and we should begin within S3 within the US-EAST-1 region.  This lab provides step by step guidance enter the information to receive the CloudSmart Insight enriched commerce analytics.
<img width="640" alt="MP Setup Customer Data Storage" src="https://user-images.githubusercontent.com/26460009/190196380-96f271a6-b897-4843-8678-b5f18c5dd017.png">

### Insert the following information from the CloudSmart tenant Registration email.

**Amazon Simple Storage Service (Amazon S3) ARN**
as an example the format is **arn:aws:s3:::bucket**

**AWS KMS ARN from the registration email**
as an example the format is **arn:aws:kms:region:account-id:key/key-id**

**SNS topic ARN - optional**
as an example the format is **arn:aws:sns:region:account-id:topicname**


## High Level Architecture  
## Revisions and Improvements
**[Feedback & Feature request view on Github](https://github.com/tvanceadv/csdataprep)**
## License
This library is licensed under the MIT-0 License. See the LICENSE file.

## Security
