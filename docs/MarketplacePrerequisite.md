![CloudSmart Logo](https://user-images.githubusercontent.com/26460009/182591613-37eaf99b-9c58-444c-94c2-8f6fb229f26d.png)
# AWS Marketplace Seller Registration

## Navigation
- [Prerequisites for AWS Marketplace Sellers (Current)](/docs/MarketplacePrerequisite.md)
- [Workshop 1: List a SaaS Subscription](/docs/Lab1.md)
- [Workshop 2: Use the AWS Marketplace Integration SaaS](/docs/Lab2.md)
- [Workshop 3: CloudSmart Data Collector](/docs/Lab3.md)

## Introduction
Joining the AWS Marketplace as a seller allows prospective customers to find, buy, and deploy your solutions alongside AWS Services. This guide will walk you through the process of registering as an AWS Marketplace seller.

### Background
Independent Software Vendors (ISVs), Data Providers, and Consulting Partners can sell their software, services, and data in AWS Marketplace to millions of AWS customers. AWS Marketplace, jointly with AWS Partner Network (APN), helps partners build, market, and sell their AWS offerings by providing valuable business, technical, and marketing support.

## Lab Overview
In this lab, you'll learn how to register as a seller on AWS Marketplace. Once you become a seller, you will be able to create products and list them in AWS Marketplace.

### Tasks
1. Register as an AWS Marketplace seller
2. Complete tax and banking information (required for paid products)

## Prerequisites

### AWS Account
- An AWS account to perform these labs
- For more information about how to create and activate an account, please see the [AWS Knowledge Center](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/)

### Business Information
- A business name and logo in a supported image format (PNG, JPG, or JPEG) with a file size of 100 KB or less
- Billing and tax information (Optional; required only if you want to list paid products)

### IAM Permissions
You must have the appropriate IAM policy permissions in your AWS account. The AWS account you use as the seller account must be activated and have a valid payment method.

> **Important**: For troubleshooting your AWS account, see [Account creation issues](https://docs.aws.amazon.com/accounts/latest/reference/troubleshoot-create-account.html) in the AWS Account Management Reference Guide.

## Task 1: Register as an AWS Marketplace Seller

> **Recommendation**: Use a new AWS account that is separate from any existing workloads. If using AWS Organizations, use a new member account instead of the management account. Note that once a product is published into a seller AWS account, it cannot be transferred to another.

1. Sign in to the [AWS account](https://console.aws.amazon.com/) that you want to use to list and manage products in AWS Marketplace.

2. As a seller, you are responsible for complying with guidelines in the [Seller Guide](https://docs.aws.amazon.com/marketplace/latest/userguide/seller-getting-started.html) and the [Terms and Conditions](https://aws.amazon.com/marketplace/management/terms) for AWS Marketplace sellers and the [AWS Customer Agreement](https://aws.amazon.com/agreement/).

3. Open the [AWS Marketplace Management Portal registration page](https://aws.amazon.com/marketplace/management/register/).

4. Enter your Legal business name. This name must be unique in AWS Marketplace.

   ![Register Form](https://github.com/tvanceadv/csdataprep/assets/26460009/ccaaf560-d06b-47b6-9731-ea9ec74b15ef)

5. Review the terms and conditions and select the "I have read and agree to the AWS Marketplace Seller Terms and Conditions" check box.

6. (Optional) Fill out the "Tell us about yourself" section.

   ![Registration Form](https://github.com/tvanceadv/csdataprep/assets/26460009/47e56880-db5e-4d1d-a488-e6e20ea2b9c0)

7. Select "Register & Sign into Management Portal".

8. After the registration is complete, you are redirected to the [AWS Marketplace Seller Profile page](https://aws.amazon.com/marketplace/management/seller-profile/).

9. Select "Add public profile" to open the public profile dialog and fill the information below:
   - For the Logo, download and upload a sample logo (or use your own logo)
   - Enter a Display Name for your profile (e.g., "My Test Company")
   - Enter a URL for your company's website (e.g., https://example.com/)
   - Enter a description about your company (e.g., "My company description here")
   - Select "Submit"

10. Wait 1-2 minutes until the account status changes to "Publish free products" before proceeding.

## Task 2: Complete Tax and Banking Information

If you want to publish paid products in AWS Marketplace, you must provide eligible [tax and banking information](https://docs.aws.amazon.com/marketplace/latest/userguide/seller-registration-process.html#seller-registration-tax-banking-step). You can add this information on the Settings page:

1. Select the "Payment information" tab.

2. Select the "Complete tax information" button and complete the form.

3. Select the "Complete banking information" button and complete the form.

4. Select the "Notifications" tab and configure an additional email address to receive notifications.

## Congratulations!
You have successfully registered as an AWS Marketplace seller. You will now be able to list products. If you provided tax and banking information, you can list paid products as well.

## Next Steps
Continue to [Workshop 1: List a SaaS Subscription](/docs/Lab1.md) to create your first product listing in AWS Marketplace.

---

## Additional Information
- For detailed instructions, please follow the link to the [CloudSmart Data Prep Workshop & Documentation](/docs/index.md).
- The purpose of this workshop is to apply the permissions required for AWS Marketplace sellers to access CloudSmart LLC's Marketplace Commerce Analytics Hub.
- If you are a new AWS Marketplace seller and would like to know more, we offer additional information on our website: [CloudSmart LLC](https://www.cloudsmart.global/)
- CloudSmart Insights is an interactive sales intelligence solution for the AWS Marketplace. CloudSmart Connect is a way to collaborate across Salesforce or HubSpot with your AWS Marketplace data. [Find us on AWS Marketplace](https://aws.amazon.com/marketplace/seller-profile?id=298cc85d-83b7-429d-87d7-b37558f4b863)

## License
This library is licensed under the MIT-0 License. See the LICENSE file.
