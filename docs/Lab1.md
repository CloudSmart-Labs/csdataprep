![CloudSmart Logo](https://user-images.githubusercontent.com/26460009/182591613-37eaf99b-9c58-444c-94c2-8f6fb229f26d.png)
# CloudSmart Insights Data Prep Workshop for AWS Marketplace

## Workshop 1: List a SaaS Subscription

### Navigation
- [Prerequisites for AWS Marketplace Sellers](/docs/MarketplacePrerequisite.md)
- [Workshop 1: List a SaaS Subscription (Current)](/docs/Lab1.md)
- [Workshop 2: Use the AWS Marketplace Integration SaaS](/docs/Lab2.md)
- [Workshop 3: CloudSmart Data Collector](/docs/Lab3.md)

## Introduction
Independent Software Vendors (ISVs), Data Providers, and Consulting Partners can sell their software, services, and data in AWS Marketplace to millions of AWS customers. AWS Marketplace, jointly with AWS Partner Network (APN), helps partners build, market, and sell their AWS offerings by providing valuable business, technical, and marketing support.

## Workshop Overview
In this lab, you'll create an initial SaaS product listing in AWS Marketplace in a limited state. Only your seller account and allowlisted test accounts can view and subscribe to this limited listing. An initial listing is required to integrate and test your application in the next labs.

### Pricing Model
This lab uses the SaaS Contract with Consumption pricing model in AWS Marketplace to demonstrate all integrations. This pricing model includes an upfront fee that is charged regardless of usage. Sellers can also send consumption reports to AWS Marketplace to charge the buyer in addition to the upfront fee. For more information on available pricing models, see [pricing models](https://docs.aws.amazon.com/marketplace/latest/userguide/pricing.html).

### Tasks
1. Create initial product listing
2. (Optional) Review your product listing

![Lab Steps Overview](https://github.com/tvanceadv/csdataprep/assets/26460009/d938cbe1-8dd9-4c6b-ac1a-065dd76d01c0)

## Prerequisites
- You must have completed the [Prerequisites for AWS Marketplace Sellers](/docs/MarketplacePrerequisite.md)
- Your seller account status on the [Settings page](https://aws.amazon.com/marketplace/management/settings/) must indicate that you can "Publish paid and free products"
- This status appears shortly after you provide eligible [tax and banking information](https://docs.aws.amazon.com/marketplace/latest/userguide/seller-registration-process.html#seller-registration-tax-banking-step)

## Task 1: Create Initial Product Listing
In this task, you publish a SaaS product into AWS Marketplace in a limited state so that you can integrate your SaaS application. Only the seller AWS account and your allowlisted test accounts are able to view and subscribe to it.

![Create Product Overview](https://github.com/tvanceadv/csdataprep/assets/26460009/7d6ce33c-ca05-4328-b7a8-da528fbaffbe)

1. Log into the [AWS Marketplace Management Portal](https://aws.amazon.com/marketplace/management/) with your AWS seller account.

   ![AWS Marketplace Management Portal](https://github.com/tvanceadv/csdataprep/assets/26460009/0d7ade19-9587-4819-b76e-85f5fb2a543d)

2. Select **Products** and then select **SaaS** in the navigation bar.
   
   ![Products Menu](https://github.com/tvanceadv/csdataprep/assets/26460009/b1e583e0-590b-4f5c-b888-d368fdfb1340)

3. Select the **Create SaaS product** dropdown menu on the right side corner of the page and then select **SaaS product** option.

4. Select **Generate product ID and product code**.
   
   ![Generate Product ID](https://github.com/tvanceadv/csdataprep/assets/26460009/29e73537-f408-48e7-aac8-e1874983fe72)

   ![Product ID Generated](https://github.com/tvanceadv/csdataprep/assets/26460009/ba6a4299-e33d-4187-80ea-3b24053453de)

5. Select **Continue**.

6. In the step **Provide product information**, use the following example values:
   - **Title** - My SaaS Product - Contract with Consumption pricing model
   - **Product logo S3 URL** - https://awsmp-logos.s3.amazonaws.com/ca60b754fe05a24257176cdbf31c4e0d
   - **Short description** - Short description goes here.
   - **Long description** - Description goes here.
   - **Highlight 1** - Highlight 1 goes here.
   - **Support details** - Support details goes here.
   - **Product categories** - Select Backup & Recovery.
   - **Keywords for search results** - my first keyword,my second keyword

   ![Provide Product Information](https://github.com/tvanceadv/csdataprep/assets/26460009/e506b40b-1612-47a6-8636-07463f71cc80)

7. Select **Next**.

8. In the step **Configure fulfillment options**, set **Fulfillment URL** to https://example.com.
   
   ![Configure Fulfillment Options](https://github.com/tvanceadv/csdataprep/assets/26460009/2ad79005-bf3e-47ea-91c3-c777cc6a0cbc)

   > **Note**: The fulfillment URL is your landing page where AWS Marketplace will redirect buyers to after they subscribe to your product (also known as your SaaS landing page or SaaS fulfillment URL). We will update this in our next lab.

9. Select **Next**.

10. In the step **Configure product pricing** use the following example values:
    - **Pricing model** - Select Contract with consumption
    - **Dimension unit type** - Select Units.

    > **Note**: The dimension type Units is useful if all of the units you charge for don't fit into one category and are a mixture. If all of the units you charge for can be defined in one of the other units, select that instead.

    **Contract dimension 1 inputs**:
    - **API identifier** - dimension_1_id
    - **Display name** - Dimension 1
    - **Description** - Dimension 1 description goes here

    > **Note**: Contract dimensions are billed automatically at the time of subscription regardless of usage.

11. Select **Add contract dimension** 2 times.

    **Contract dimension 2 inputs**:
    - **API identifier** - dimension_2_id
    - **Display name** - Dimension 2
    - **Description** - Dimension 2 description goes here

    **Contract dimension 3 inputs**:
    - **API identifier** - dimension_3_id
    - **Display name** - Dimension 3
    - **Description** - Dimension 3 description goes here

12. Select **Add usage dimension** 3 times.

    **Usage dimension 1 inputs**:
    - **API identifier** - metered_1_id
    - **Description** - Metered dimension 1 desc goes here

    > **Note**: Usage dimensions (also referred to as usage-based dimensions, consumption-based dimensions, metered dimensions, or out-of-contract dimensions) are not billed automatically. Your application must report usage for AWS Marketplace to charge the buyer these dimensions.

    **Usage dimension 2 inputs**:
    - **API identifier** - metered_2_id
    - **Description** - Metered dimension 2 desc goes here

    **Usage dimension 3 inputs**:
    - **API identifier** - metered_3_id
    - **Description** - Metered dimension 3 desc goes here

    > **Important**: After your product is published live, you cannot remove dimensions or change the API identifier of existing dimensions.

13. Select **Next**.

14. In the step **Set prices**, use the following example values:
    
    ![Set Prices](https://github.com/tvanceadv/csdataprep/assets/26460009/286ca27f-142a-46ac-af35-1c23926bb232)

    - **Purchasing options** - Keep the default Multiple dimensions per contract. This allows your buyers to specify the number of units they would like to purchase when they subscribe to your product (also known as configurable dimensions).
    - **Contract duration options** - select 1 month and 12 months.

    > **Important**: Prices in Test pricing for contract dimensions are set to 0.001 until you are ready to publish to allow testing without incurring a large bill.

15. Select **Next**.

16. In the step **Specify refund policy**, set **Refund policy** to "Refund and cancellation policy goes here."
    
    ![Specify Refund Policy](https://github.com/tvanceadv/csdataprep/assets/26460009/5cc842d8-d829-477c-ba3b-bbaf8be62189)

17. Select **Next**.

18. In the step **Configure EULA**, keep the default **Standard Contract for AWS Marketplace (SCMP)** option selected.
    
    ![Configure EULA](https://github.com/tvanceadv/csdataprep/assets/26460009/99df19cf-3108-4ed2-beb2-a256e2fbe981)

    > **Note**: To attach a custom end-user license agreement, select Custom EULA and provide an S3 link to the agreement.

19. Select **Next**.

20. In the step **Configure offer availability**, keep the default **All countries** option.
    
    ![Configure Offer Availability](https://github.com/tvanceadv/csdataprep/assets/26460009/b04e05ee-bc7b-44a3-90f8-f8bc11e32792)

    > **Note**: For your actual listing, you can restrict your product to AWS accounts in specific locations. For more information, see [Regions and countries for your AWS Marketplace product](https://docs.aws.amazon.com/marketplace/latest/userguide/regions-and-countries.html) in the AWS Marketplace Seller Guide.

21. Select **Next**.

22. In the step **Configure allowlist**, leave the field blank for this lab.
    
    ![Configure Allowlist](https://github.com/tvanceadv/csdataprep/assets/26460009/a31caf0b-fde0-4075-aad3-1ecc0837587c)

    All new product listings published to AWS Marketplace start out with limited visibility. You can control which accounts have access to your limited product by allowlisting select AWS account IDs. This allows you to test the product usage and experience before publishing. The account that you're using to create this listing request is allowed by default.

23. Select **Submit** to create a new change request to submit your product for publishing to limited visibility for testing.
    
    ![Submit Request](https://github.com/tvanceadv/csdataprep/assets/26460009/a6807b81-c0a8-47b0-8dc3-8509353fe5ce)

24. Wait 10-15 minutes until your request status is in the **Succeeded** state. If the request fails, the reason will be displayed.

    When you refresh the page, you may get the error: "We can't find the page you're looking for..." This may appear while your product is applying changes. You can either wait and refresh again or check the status of your request in the [Requests page](https://aws.amazon.com/marketplace/management/requests/) in the AWS Marketplace Management Portal.

    > **Tip**: If you navigate away from this page, you can find your request in the [Requests page](https://aws.amazon.com/marketplace/management/requests/) in the AWS Marketplace Management Portal.

## Congratulations!
You have successfully created an initial SaaS product listing in AWS Marketplace!

## Task 2: (Optional) Review Your Product Listing
In this task, you review your product details in AWS Marketplace.

![Review Product](https://github.com/tvanceadv/csdataprep/assets/26460009/74567bf2-4a1d-4c7c-819a-d97e173cc024)

> **Wait!** Before continuing, wait until the request created in the previous task shows a status of **Succeeded**.

1. Open the [SaaS products page](https://aws.amazon.com/marketplace/management/products/saas) in the AWS Marketplace Management Portal.

2. Select your SaaS product in the list.

3. Select **View on AWS Marketplace**.

4. Review your product detail page in AWS Marketplace for accuracy.

5. Select **View purchase options**.
   
   ![View Purchase Options](https://github.com/tvanceadv/csdataprep/assets/26460009/5b4d9dc0-7631-49b9-a216-708e65b04861)

6. Review your pricing details.

   > **Button disabled?** If the View purchase options button is disabled and you see the error "You don't have the AWS account credentials to view this information", this is caused by a temporary delay in publishing. Wait 15-30 minutes and refresh the page.

## Congratulations!
You have successfully reviewed your product details in AWS Marketplace!

You now have two options in this workshop. You can walk through the required integration and the APIs involved or you can deploy a sample SaaS integration framework to see how end-to-end integration works.

## Next Steps
Continue to [Workshop 2: Setting Up the AWS Marketplace Integration SaaS](/docs/Lab2.md) to create an integration between your product and AWS Marketplace.

## Clean Up Instructions
No action required. AWS Marketplace currently does not have the functionality to completely delete product listings submitted for publishing from a seller account.

---

[Return to Workshop Index](/docs/index.md)