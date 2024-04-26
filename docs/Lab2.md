## Lab: Integrate your SaaS (with AWS Quick Start example)
#### Background
With software as a service (SaaS) products, you deploy and manage software in your AWS account and grant buyers access to the application. You are responsible for managing customer access, account creation, resource provisioning, and account management within your software.

#### Lab overview
AWS Marketplace offers an AWS Partner Solution to streamline the integration of SaaS products with AWS Marketplace. In this lab, you will set up this solution for the product that you have created in the Lab: Create a SaaS listing.

Task 1: Deploy the Serverless SaaS Integration AWS Partner solution

Task 2: Confirm the Amazon SNS subscription

Task 3: Update your product with the new registration page URL

Task 4: Modify and upload your registration page

Task 5: Simulate the buyer experience

Task 6: Check entitlement and add metering records

#### Diagram of tasks in this lab

The solution is a lightweight serverless implementation that provides the core capabilities required to integrate your SaaS solution with its corresponding listing in AWS Marketplace. The solution's capabilities include accepting new customer registrations, granting and revoking customer access, updating customer entitlements, and reporting metered usage. For more information, see AWS Marketplace Serverless SaaS Integration on AWS .

Diagram of the components of the Serverless SaaS Integration AWS Partner solution

#### Prerequisites
The prerequisites can be referenced [here.](/docs/MarketplacePrerequisite.md)
Intro to Marketplace Listing
The first lab is a guided SaaS Subscription Listing.  What is SaaS Subscription in the AWS Marketplace context? https://docs.aws.amazon.com/marketplace/latest/userguide/saas-subscriptions.html

SaaS Subscription is a software listing that has a base price and allows for metered usage charges. The usage charges are not required and can the dimensions can be added later.

Lab 1: List a SaaS Subscription [Lab1](/docs/Lab1.md)

#### Pricing model
This lab uses the SaaS Contract with Consumption pricing model in AWS Marketplace to demonstrate all integrations. This pricing model includes an upfront fee that is charged regardless of usage. Sellers can also send consumption reports to AWS Marketplace to charge the buyer in addition to the upfront fee. For more information on available pricing models, see pricing models.
Your product details - These details include your product code and Amazon Simple Notification Service (SNS)  topics for your product. To find these details, open the SaaS products page , select your product, and view the Product summary.
An email ID - An email (distribution list) to receive notifications every time someone subscribes to your product.
You must have the following policy permissions in your AWS account.
IAM policies required
Task 1: Deploy the Serverless SaaS Integration AWS Partner solution
In this task, you will use the AWS CloudFormation console to automatically create the resources required for integrating your product with the AWS Marketplace in your seller account.

Launch the stack using the AWS CloudFormation console.

Launch stack View template

More information
The AWS Marketplace Serverless SaaS Integration on AWS (Quick Start)  uses the source in the aws-samples/aws-marketplace-serverless-saas-integration  GitHub repository.
Verify that you are in the N. Virginia (us-east-1) region and press on Next.

Screenshot of the AWS CloudFormation console

For the Stack name, leave the default value of marketplace-saas or use another stack name that is unique in your AWS account for that AWS Region.

For the S3 bucket name, input a globally unique name for the S3 bucket where the sample registration page is hosted.

For the Product code, replace the PRODUCTCODE in the input with the product code for your product.

Note
You can also find the product code by viewing the details of your product on the SaaS products page  in the seller portal.
For the Subscriptions SNS topic ARN, replace the PRODUCTCODE at the end of the input with your product code.

For the Entitlements SNS topic ARN, replace the PRODUCTCODE at the end of the input with your product code.

Note
Confirm that the AWS account IDs in the ARNs match the ones in your Product summary for your product in the SaaS product page .
For the Admin email address, input the email where you want to receive SNS notifications for new buyer registrations, entitlement changes, and subscription events.

Note
Do not change the Artifact S3 bucket name.
Screenshot of filling out the template parameters in the AWS CloudFormation console

Check both the following checkboxes:

I acknowledge that AWS CloudFormation might create IAM resources with custom names.

I acknowledge that AWS CloudFormation might require the following capability: CAPABILITY_AUTO_EXPAND.

Select Create stack.

Screenshot of options before launching a template in the AWS CloudFormation console

The solutions will be deployed in your account. This process takes around 5-15 min.

Task 2: Confirm the Amazon SNS subscription
To receive email notifications at the email address you provided during the solution deployment, you need to confirm the SNS subscription to the newly deployed SNS topic.

Open your email inbox and find the email with the subject AWS Notification - Subscription Confirmation.

In the email, select Confirm subscription.

Screenshot of email from Amazon SNS requesting confirmation of email subscription

You will now receive an email for new buyer registrations, entitlement changes, and subscription events.

Task 3: Update your product with the new registration page URL
As part of the setup process, you need to update your product's registration page URL so that AWS Marketplace redirects buyers to your new registration page after they subscribe.

Back in the AWS CloudFormation console  where the solution was deployed, select the NESTED stack that was deployed. The stack name looks similar to the following: marketplace-saas-SampleApp-EXAMPLE123.

Select the Outputs tab in the stack details.

Note
If the Outputs tab is empty, wait until the stack status shows CREATE_COMPLETE.
Copy the value of the LandingPageUrl output. It looks similar to the following: https://example123.cloudfront.net/index.html.

Screenshot of the Outputs tab of the AWS CloudFormation console that highlights the LandingPageUrl value

Open SaaS product  page in the AWS Marketplace Management Portal.

Select the product you created in the Lab: Create a SaaS listing.

Note
If you do not have a product staged in limited in AWS Marketplace yet, complete the Lab: Create a SaaS listing to create one. A product staged in limited is only accessible from the seller account or allowlisted test accounts.
Select the dropdown menu Request changes and then select Update fulfillment options.

Screenshot of selecting the Update fulfillment options menu option in the seller portal

Change the value in the Fulfillment URL to the value you copied from the Outputs tab earlier.

Select Submit and wait 5-10 minutes for the Request status to show Succeeded. Refresh the page to see the latest status.

Screenshot of a request status succeeded in the seller portal

Wait!
You must wait for the Request status to show Succeeded before continuing. Refresh this page every few minutes until it does.
You've just updated your product in AWS Marketplace to redirect buyers to the newly deployed registration page after they subscribe.

Task 4: Modify and upload your registration page
You need to modify your static sample registration page to connect to the API endpoint of the solution you have just deployed.

Back in the AWS CloudFormation console  where the solution was deployed, select the NESTED stack that was deployed. The stack name looks similar to the following: marketplace-saas-SampleApp-EXAMPLE123.

Select the Outputs tab in the stack details.

Copy the value of the APIUrl output. It looks similar to the following: https://example123.execute-api.us-east-1.amazonaws.com/Prod/.

Screenshot of the Outputs tab of the AWS CloudFormation console that highlights the APIUrl

Download the ZIP file containing the static registration page.

Download ZIP View source

Unzip the file and open the web folder to access the files inside.

Open the file named scripts.js and update the baseUrl property in line 1 with the APIUrl you copied in step 3.

Before:

1
const baseUrl = 'https://API-ID.execute-api.us-east-1.amazonaws.com/Prod/'; // TODO: This needs to be replaced
Example of line 1 after the change:

1
const baseUrl = 'https://example123.execute-api.us-east-1.amazonaws.com/Prod/'; // TODO: This needs to be replaced
Important
It is important that the URL accurately matches the value from the stack output including the trailing slash.
Save the file.

Open the Amazon S3 console .

Select the S3 bucket with the name that you specified in task 1 for the S3 bucket name parameter when launching the stack.

Select Upload and follow the prompts to upload the 5 files in the web folder to the S3 bucket.

Screenshot of successfully uploading objects to an S3 bucket in the S3 console

You've just added the static web files to the S3 bucket modefied with values unique to this deployment.

Task 5: Simulate the buyer experience
Now, you will simulate the buyer experience by subscribing to your product. We will also check that all of our product metadata is as we expect it to be.

Open SaaS product  page in the AWS Marketplace Management Portal.

Select the product you created in the Lab: Create a SaaS listing.

Select View on AWS Marketplace.

Here you can review that your product information is accurate.

Screenshot of the seller portal that highlights the View on AWS Marketplace button

Select View purchase options.

Under How long do you want your contract to run?, select 1 month.

Set your Renewal Settings to No.

Under Contract Options, set any option quantity to 1 (or select the cheapest option tier, if applicable).

Select Create contract and then Pay now.

Note
Generally for testing, the AWS Marketplace sets your price to $0 or $0.001 so you are not significantly charged during testing. If you see your own software charges on your AWS bill, as the seller, you can initiate a refund  for yourself or your test account.
Screenshot of a product procurement page that highlights the Create contract button

Select Set up your account

Screenshot of a prompt that highlights the Set up your account button after subscribing

At this point you will be redirected to the registration page we modified and uploaded in Task 4: Modify and upload your registration page. Here your buyers submit their registration information which gets sent to the email you confirmed in Task 2: Confirm the Amazon SNS subscription.

Fill the information in the registration page.

Select Register.

Screenshot of the SaaS landing page that is filled out and that highlights the Register button

After a few seconds, a blue banner should appear letting you know that the registration has completed successfully. Also, you should have an email with the subscription details in your notification email inbox as the one shown below.

Screenshot of an email notification that a new buyer has successfully subscribed

You've now seen how this solution allows buyers to submit their contact information after subscribing in AWS Marketplace.

Task 6: Check entitlement and add metering records
In this lab, you configured the solution for your SaaS product with the pricing model Contract with Consumption. This pricing comprises of two components: the contract (also referred to as the entitlements, in-contract dimensions, prepaid dimensions) and the consumption (also referred to as out-of-contract dimensions, usage-based dimensions, consumption-based dimensions, or metered dimensions). The solution will make the necessary API calls to AWS Marketplace on your behalf.

In this task, you'll learn where the solution stores the entitlement information and where you will add metering records so they get reported to AWS Marketplace.

Open the Explore items  page in the Amazon DynamoDB console.

You should see the 2 following tables: AWSMarketplaceSubscribers and AWSMarketplaceMeteringRecords.

Select the AWSMarketplaceSubscribers table.

Screenshot of the DynamoDB console showing the AWSMarketplaceSubscribers table

This table contains user registration data as well as their contract details (also known as entitlements). Every time there is an update in the buyer's contracts such as contract expiration, contract upgrade, or renewal, this table will be automatically updated.

Take note of the customerIdentifier. This is used in the following steps to add consumption records for this buyer.

Now, select the AWSMarketplaceMeteringRecords table. It should be empty.

Metering information that should be reported to AWS Marketplace should be stored in this AWSMarketplaceMeteringRecords DynamoDB table.

In the following steps, you will insert a record into that table so the solution can report it to AWS Marketplace and your buyers are charged for addtional consumption.

Note
For demonstration, we will manually insert a record. In production, you automatically insert records based on monitoring your buyers' consumption of your application. AWS Marketplace does not monitor or track your buyers' consumption of your SaaS application.
Open AWS CloudShell .

Run the following command to get the current timestamp (for example, 1678672031).

date +%s

Take note of the output value by copying it to somewhere outside of AWS CloudShell because you will need it later. It looks similar to the following: 1678672031.

Run the following command in the terminal to open a text editor and create the metering record.

vim metering_record.json

Screenshot of AWS CloudShell ediing a metering record JSON file

Type i to switch to INSERT mode.

Copy and paste the following JSON and replace the following placeholders.

<CURRENT_TIMESTAMP> - Replace with the timestamp you copied previously.
<CUSTOMER_IDENTIFIER> - Replace with the value of the customerIdentifier you took note of earlier.
<USAGE_DIMENSION_1> - Replace with one of the API names you specified for an out-of-contract dimension. If you've been using examples provided in the lab to create your product listing, you can use metered_1_id.
<USAGE_DIMENSION_2> - Replace with one of the API names you specified for an out-of-contract dimension. If you've been using examples provided in the lab to create your product listing, you can use metered_2_id.
Tip
Editing in vim may be difficult if this is your first time. You can instead copy the following JSON to your text editor and replace the placeholders there before pasting it into AWS CLoudShell.
{
    "create_timestamp": { "N": "<CURRENT_TIMESTAMP>" },
    "customerIdentifier": { "S": "<CUSTOMER_IDENTIFIER>" },
    "dimension_usage": { "L": [
            {
                "M": {
                    "dimension": { "S": "<USAGE_DIMENSION_1>" },
                    "value": { "N": "10" }
                }
            },
            {
                "M": {
                    "dimension": { "S": "<USAGE_DIMENSION_2>" },
                    "value": { "N": "10"}
                }
            }]
    },
    "metering_pending": { "S": "true" }
}

Note
The "value": { "N": "10"} is the number of units of a dimension the buyer has used in your SaaS application.
To exit INSERT mode, press the ESC key.

To save and quit, type :wq and press the *Enter key.

To insert the JSON record we just created into the metering record table run, the following put-item AWS CLI command .

aws --region us-east-1 dynamodb put-item --table-name AWSMarketplaceMeteringRecords --item file://metering_record.json

To verify the new item, return to the Explore items  page in the Amazon DynamoDB console.

Select the AWSMarketplaceMeteringRecords table and you should see the table is now no longer empty and includes the item we added.

Select this new item.

Select the expand icon () next to the column header Attribute name to expand all nested attributes.

You'll notice that the attribute metering_pending has a value of true. This means this record has not yet been reported to AWS Marketplace. The solution aggregates and reports consumption once per hour automatically.

Note
It is important to add metering records every hour to this table because AWS Marketplace only accepts metering records for 1 additional hour after the contract expires (or for usage-based pricing, when the subscription is cancelled).
Important
The solution automatically sends the metering records in this table to AWS Marketplace every hour. However, for this lab, we will trigger this process manually so that we can see the response and test whether our dimensions are reported correctly.
To trigger the reporting manually, open a new browser tab to the Functions  page in the AWS Lambda console.

Select the function name that begins with the stack name you specified in task 1 and that also includes -Hourly- in the name. It looks similar to the following: marketplace-saas-SampleApp-EXAMPLE123-Hourly-EXAMPLE456.

Select the Test tab and then select the Test button.

In a few seconds, you should see a green banner showing Execution result: succeeded.

Screenshot of the AWS Lambda console that highlights the Test tab and button

Return to the previous browser tab to verify that the item of our consumption record was successfully reported to AWS Marketplace.

This is the browser tab where you were viewing the added item in the AWSMarketplaceMeteringRecords table within the Explore items  page in the Amazon DynamoDB console.

Refresh the browser page and notice that the record has changed. It now has 2 new attributes named metering_response and metering_failed.

If everything worked as expected, the metering_failed value should have False selected and the metering_response value should contain the response of the BatchMeterUsage API action  call.

Congratulations!
You've just completed the requred integration for publishing a SaaS product.

It is recommended that you further integrate your SaaS application into this solution to automate the provisioning of your SaaS application for buyers and to automate the adding of consumption records for reporting.

When you are ready to publish your product live and make it publicly available, select your product in the SaaS product page , select Request changes, choose Update product visibility, and follow the prompts.

Clean up instructions
Open the Buckets  list in the Amazon S3 console.

Locate the bucket hosting the web files created by the AWS CloudFormation stack. The bucket name is the value that you specified in task 1 for the S3 bucket name parameter when launching the stack. It is the WebsiteS3Bucket resource in the AWS CloudFormation template.

Select the radio button next to that bucket, select Empty, and follow the prompts to delete all objects in the bucket.

Return to the Buckets  list in the Amazon S3 console.

Now, locate the bucket created by the AWS CloudFormation stack for storing logs. The bucket name is the value that you specified in task 1 for the S3 bucket name parameter when launching the stack with -log appended at the end (for example, mybucketname123-log). It is the WebsiteS3BucketLog resource in the AWS CloudFormation template.

Select the radio button next to the bucket, select Empty, and follow the prompts to delete all objects in the bucket.

Note
You can confirm the bucket names by referring to the Resources tab in the AWS CloudFormation console for the NESTED stack created by the Quick Start.
Open AWS CloudFormation console .

Locate and select the AWS CloudFormation stack created by the Quick Start. Do not select the stack tagged with NESTED. Select the main stack instead.

Select Delete.

Wait!
This initial deletion will fail! Make sure to return after 3 to 24 hours and try again.
Why does the initial deletion fail?
This initial deletion is expected to fail because it will be able remove all resources except for the AWS Lambda function. The solution replicates AWS Lambda functions to edge locations in Amazon CloudFront. These replicas can take anywhere from 3 to 24 hours to delete.
Wait 3 to 24 hours and select Delete again.
