![FullColor250](https://user-images.githubusercontent.com/26460009/182591500-ac99b0d8-2639-4a28-8357-97d09e0e2063.png)
# CloudSmart Data Prep Workshop for AWS Marketplace

Customer Data Prep Workshop for CloudSmart LLC

## Introduction
CloudSmart customers are sellers within the AWS Marketplace and are looking for insights into their sales activities.  Our goal in this data prep workshop is to create the guardrails and least security principle access to that data.  Ultimately that data will be consumed by the CloudSmart Commerce Engine to provide meaningful sales analytics, reporting, and connectivity to customers.
## Pre-requisites
An AWS Account is required. Basic knowledge of AWS foundational services such as Identity and Access Management (IAM) and Amazon S3 are strongly encouraged.  Given that this dataset is based on the AWS Marketplace, being a seller in the AWS Marketplace is also required. Access to the AWS Account associated with the marketplace management portal and appropriate IAM permissions are also necessary. see https://docs.aws.amazon.com/marketplace/latest/userguide/data-feed.html

Before getting beginning the workshop, you need to follow these preparation steps. The workshop is designed with a "bring your own data" mindset, these instructions are here to help you prepare your own dataset.

## Additional Pre-requisite for AWS Marketplace Sellers
To access data feeds, you need to configure your environment to receive data feeds to an encrypted Amazon S3 bucket. AWS Marketplace provides an AWS CloudFormation template that you can use to simplify configuration. https://s3.amazonaws.com/aws-marketplace-reports-resources/DataFeedsResources.yaml

## Setting up the environment
AWS Marketplace Sellers and the AWS Marketplace Sales data are located within US-EAST-1 and we should begin within S3 within the US-EAST-1 region.  This lab provides step by step guidance to store the data in a cost-optimized Amazon S3 bucket and perform minimal transformation within a customer account.

## Data Prep within customer account - Reference Solution for AWS Marketplace Data 
We will prepare our data using Apache Parquet.  Parquet is a columnar storage format and is used to provide efficient storage and performance benefits.  For background please refer to https://blog.openbridge.com/how-to-be-a-hero-with-powerful-parquet-google-and-amazon-f2ae0f35ee04

For our purposes we will be using AWS Glue Databrew.  AWS Glue DataBrew is a visual data preparation tool that enables users to clean and normalize data without writing any code.  This is ideal for following along without a significant amount of coding.  <img width="788" alt="image" src="https://user-images.githubusercontent.com/26460009/182211415-d7756116-1703-4a4c-a929-f1915bb30f45.png">

Select connect a new Dataset
Add details such as the Dataset name:
<img width="667" alt="image" src="https://user-images.githubusercontent.com/26460009/182212314-27cd374a-757e-4854-804d-fc755e8e17d2.png">

Next Enter your source from S3:  This will be the location that your AWS Seller DataFeed is stored in S3.  Browse if applicable to the bucket containing the AccountFeed_V1 and the other folders of seller information.  (repeat for each folder)

The data is currently in CSV format and you must select CSV.

Select the specific folder and create the dataset (First folder AccountFeed_V1 and repeat for each folder)

<img width="296" alt="image" src="https://user-images.githubusercontent.com/26460009/182213167-7e595bc2-ec3a-4e98-abec-3226f9424b6d.png">

Next view the dataset by opening Databrew>Datasets and selecting Datasets.  You should see the dataset you created in the previous step.
Select it and then click "Create project with this dataset"
<img width="888" alt="image" src="https://user-images.githubusercontent.com/26460009/182213888-1657a4a9-4312-4a9c-bfa3-aa62e7738399.png">

Select Create Project
Within your project enter a project-name.  This will also create a recipe.
<img width="596" alt="image" src="https://user-images.githubusercontent.com/26460009/182211856-6f48ef12-23ab-4ed6-8ea0-1e5a8b3154a5.png">
Your dataset should be selected.

Permissions should be using the principle of least privilege:  
Define a new IAM role and follow the suggestion to "suffix with "AWSGlueDataBrewServiceRole-data" with data being provided in the dialog box such as AWSGlueDataBrewServiceRole-data

<img width="881" alt="image" src="https://user-images.githubusercontent.com/26460009/182215323-656420ae-99b3-4f3f-9d4c-c931d3e9e1cf.png">

Select "Create project" to complete the project setup.

Open Amazon S3 in a new window or tab to create an output folder for the job output.

In Amazon S3 select "Create bucket"  name the bucket according to your standards.  Optionally, select Server-side encryption with AWS KMS key (SSE-KMS)

<img width="352" alt="image" src="https://user-images.githubusercontent.com/26460009/182220578-55bba3c9-2408-4a85-85df-c18b3537f6c4.png">

Return to AWS Glue Databrew
Next Select Jobs from the AWS Glue Databrew console

Select Create Job and enter a job name
Under Job type select Create a recipe job
Under Job input run on Dataset and select the previously created dataset by "Browse datasets"

Repeat for each folder within the marketplace seller datafeeds.

Run the jobs for each folder to create the output files.

## High Level Architecture  
## Revisions and Improvements
**[Feedback & Feature request view on Github]** | **[Documentation](https://github.com/tvanceadv/csdataprep)**
## License
This library is licensed under the MIT-0 License. See the LICENSE file.

## Security
