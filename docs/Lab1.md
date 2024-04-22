![FullColor250](https://user-images.githubusercontent.com/26460009/182591613-37eaf99b-9c58-444c-94c2-8f6fb229f26d.png)
# Joining the AWS Marketplace as a Seller allows prospective customers to find, buy, and deploy your solutions alongside the AWS Services.
Register as an AWS Marketplace seller
Background
Independent Software Vendors (ISVs), Data Providers, and Consulting Partners can sell their software, services, and data in AWS Marketplace to millions of AWS customers. AWS Marketplace, jointly with AWS Partner Network (APN) , helps ISVs and Consulting Partners to build, market, and sell their AWS offerings by providing valuable business, technical and marketing support.

## Lab overview
In this lab, you'll create an initial listing
Lab overview
In this lab, we create an initial product listing in AWS Marketplace in a limited state. Only your seller account and allowlisted test accounts can view and subscribe to this limited listing. An initial listing is required to integrate and test your application in the next labs.

### Pricing model
This lab uses the SaaS Contract with Consumption pricing model in AWS Marketplace to demonstrate all integrations. This pricing model includes an upfront fee that is charged regardless of usage. Sellers can also send consumption reports to AWS Marketplace to charge the buyer in addition to the upfront fee. For more information on available pricing models, see pricing models.
Task 1: Create initial product listing
Task 2: (Optional) Review your product listing
Lab steps

### Prerequisites
You must have an AWS account registered as a seller in AWS Marketplace.
Tax and banking information required
This lab requires that your seller account status on the Settings page  indicates that you can Publish paid and free products. This status appears shortly after you provide eligible tax and banking information .

You must have the following policy permissions in your AWS account.
IAM policies required
Task 1: Create initial product listing
In this task, you publish a SaaS product into AWS Marketplace in a limited state so that you can integrate your SaaS application. Only the seller AWS account and your allowlisted test accounts are able to view and subscribe to it.

Log into the AWS Marketplace Management Portal  with your AWS seller account.

Select Products and then select SaaS in the navigation bar.

Products menu in seller portal

Select the Create SaaS product dropdown menu on the right side corner of the page and then select SaaS product option.

Create Product

Select Generate product ID and product code.

Generate product ID

Select Continue.

Product ID generated

In the step Provide product information, use the following example values.

Title - My SaaS Product - Contract with Consumption pricing model

Product logo S3 URL - https://awsmp-logos.s3.amazonaws.com/ca60b754fe05a24257176cdbf31c4e0d

Short description - Short description goes here.

Long description - Description goes here.

Highlight 1 - Highlight 1 goes here.

Support details - Support details goes here.

Product categories - Select Backup & Recovery.

Keywords for search results - my first keyword,my second keyword

Provide product information

Select Next.

In the step Configure fulfillment options, set Fulfillment URL to https://example.com.

Note
The fulfillment URL is your landing page where AWS Marketplace will redirect buyers to after they subscribe to your product (also known as your SaaS landing page or SaaS fulfillment URL). We will update this in our next lab.
Configure fulfillment options

Select Next.

In the step Configure product pricing use the following example values.

Pricing model - Select Contract with consumption

Dimension unit type - Select Units.

Note
The dimension type Units is useful if all of the units you charge for don't fit into one category and are a mixture. If all of the units you charge for can be defined in one of the other units, select that instead.
Contract dimension 1 inputs:

API identifier - dimension_1_id

Display name - Dimension 1

Description - Dimension 1 description goes here

Note
Contract dimensions are billed automatically at the time of subscription regardless of usage.
Select Add contract dimension 2 times.

Contract dimension 2 inputs:

API identifier - dimension_2_id

Display name - Dimension 2

Description - Dimension 2 description goes here

Contract dimension 3 inputs:

API identifier - dimension_3_id

Display name - Dimension 3

Description - Dimension 3 description goes here

Select Add usage dimension 3 times.

Usage dimension 1 inputs:

API identifier - metered_1_id

Description - Metered dimension 1 desc goes here

Note
Usage dimensions (also referred to as usage-based dimensions, consumption-based dimensions, metered dimensions, or out-of-contract dimensions) are not billed automatically. Your application must report usage for AWS Marketplace to charge the buyer these dimensions.
Usage dimension 2 inputs:

API identifier - metered_2_id

Description - Metered dimension 2 desc goes here

Usage dimension 3 inputs:

API identifier - metered_3_id

Description - Metered dimension 3 desc goes here

Important
After your product is published live, you cannot remove dimensions or change the API identifier of existing dimensions.
Select Next.

In the step Set prices, use the following example values.

Purchasing options - Keep the default Multiple dimensions per contract. This allows your buyers to specify the number of units they would like to purchase when they subscribe to your product (also known as configurable dimensions).

Contract duration options - select 1 month and 12 months.

Set prices

Important
Prices in Test pricing for contract dimensions are set to 0.001 until you are ready to publish to allow testing without incurring a large bill.
Select Next.

In the step Specify refund policy, set Refund policy to Refund and cancellation policy goes here..

Specify refund policy

Select Next.

In the step Configure EULA, keep the default Standard Contract for AWS Marketplace (SCMP) option selected.

Configure EULA

Note
To attach a custom end-user license agreement, select Custom EULA and provide an S3 link to the agreement.

Select Next.

In the step Configure offer availability, keep the default All countries option.

Configure offer availability

Note
For your actual listing, you can restrict your product to AWS accounts in specific locations. For more information, see Regions and countries for your AWS Marketplace product  in the AWS Marketplace Seller Guide.
Select Next.

In the step Configure allowlist, leave the field blank for this lab.

All new product listings published to AWS Marketplace start out with limited visibility. You can control which accounts have access to your limited product by allowlisting select AWS account IDs. This allows you to test the product usage and experience before publishing. The account that you're using to create this listing request is allowed by default.

Configure allowlist

Select Submit to create a new change request to submit your product for publishing to limited visibility for testing.

Wait 10-15 minutes until your request status is in the Succeeded state. If the the request fails, the reason will be displayed.

When you refresh the page, you may get the error: We can't find the page you're looking for... This may appear while your product is applying changes. You can either wait and refresh again or check the status of your request in the Requests page  in the AWS Marketplace Management Portal.

AMMP SaaS - Error after submitting and refreshing page.

Tip
If you navigate away from this page, you can find your request in the Requests page  in the AWS Marketplace Management Portal.

Congratulations!
You have successfully created an initial SaaS product listing in AWS Marketplace!

Task 2: (Optional) Review your product listing
In this task, you review your product details in AWS Marketplace.

Wait!
Before continuing, wait until the request created in the previous task shows a status of Succeeded.
Open the SaaS products page  in the AWS Marketplace Management Portal.

Select your SaaS product in the list.

Select View on AWS Marketplace.

Review your product detail page in AWS Marketplace for accuracy.

Demo product

Select View purchase options.

Review your pricing details.

Button disabled?
If the View purchase options button is disabled and you see the error You don't have the AWS account credentials to view this information, this is caused by a temporary delay in publishing. Wait 15-30 minutes and refresh the page.

Product detail page error for initial publishing

Congratulations!
You have successfully reviewed your product details in AWS Marketplace!
You now have two options in this workshop. You can walk through the required integration and the APIs involved or you can deploy a sample SaaS integration framework to see how end-to-end integration works.

Clean up instructions
No action required
There is no cleanup step required. AWS Marketplace currently does not have the functionality to completely delete product listings submitted for publishing from a seller account.


# [CloudSmart Data Prep Workshop & Documentation](/docs/index.md)
For detailed instructions please follow the link to the documentation. 
The purpose of this workshop is apply the permissions required for AWS Marketplace sellers to access CloudSmart LLC's Marketplace Commerce Analytics Hub.

This repo and documentation is used as a primer customers that leverage the AWS Marketplace and CloudSmart Commerce Analytics Hub. 

If you are a new AWS Marketplace seller and would like to know more, we offer additional information on our website.  [CloudSmart LLC](https://www.cloudsmart.global/)

CloudSmart Insights is an interactive sales intelligence solution for the AWS Marketplace.  CloudSmart Connect is a way to collaborate across Salesforce or HubSpot with your AWS Marketplace data. [Find us on AWS Marketplace](https://aws.amazon.com/marketplace/seller-profile?id=298cc85d-83b7-429d-87d7-b37558f4b863)
## License
This library is licensed under the MIT-0 License. See the LICENSE file.

## Security
