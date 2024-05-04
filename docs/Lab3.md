![FullColor250](https://user-images.githubusercontent.com/26460009/182591500-ac99b0d8-2639-4a28-8357-97d09e0e2063.png)
# CloudSmart Insights Data Prep Workshop for AWS Marketplace

Customer Data Prep Workshop for CloudSmart LLC

## Data Prep Installation.
CloudSmart Insights onboarding occurs in two parts. First, the creation of the CloudSmart SaaS tenant, which permits the data collector to aggregate the Marketplace data.  Second, the creation of tenant resources to copy data.
![CloudSmartBadge](https://user-images.githubusercontent.com/26460009/183915211-2252735e-bf8f-4ffa-b619-c14e4ae59436.png)


#### INPUT/PARAMETERS : 
Source Account ID (Client AWS Account 12 digits) - Root FolderName (The digits from the Tenant name created in the Saas application)

Suffix ( Required! : to no fall into bucket already exists error) 
Destination Account ID
(Set to 044080027516 )
![image](https://github.com/tvanceadv/csdataprep/assets/26460009/d12f0042-6aa5-4b81-9e7c-c577f92a8599)
![image](https://github.com/tvanceadv/csdataprep/assets/26460009/7d534e73-9e96-4881-8eb0-66b40caeaaa3)
![image](https://github.com/tvanceadv/csdataprep/assets/26460009/a9a266cf-04f9-4a42-8c3c-0f86546c0da5)
![image](https://github.com/tvanceadv/csdataprep/assets/26460009/510834a5-7883-486a-8122-3e3bed2d0e1b)

![image](https://github.com/tvanceadv/csdataprep/assets/26460009/11ab6ada-f9a2-4804-896b-dd93d68e8c38)


Launch v1 Stack (New Enrollment to AWS Marketplace SDDS) [CloudSmart Data Collector](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create?&templateURL=https://cloudsmartglobalpub.s3.amazonaws.com/FinalTemplate.yml)

Launch v2 Stack (Existing Enrollment to AWS Marketplace SDDS) [CloudSmart Data Collector for Existing SDDS Users](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create?&templateURL=https://cloudsmartglobalpub.s3.amazonaws.com/FinalTemplateV2.yml)

#### RESOURCES : The template deploys the following resources
S3 Bucket
Bucket Policy
KMS Key
KMS Key Alias
Lambda Function (establishes the sync between our bucket and the client bucket)
Lambda Function Role
Lambda Invoke Permission
Custom Resources : Lambda Function - Lambda Function Trigger (adding the S3 bucket notification and
allowing the lambda to get triggered)

#### We deploy an S3 bucket encrypted with a KMS key
Where the tenant will set them up in his AWS Marketplace Account, so that whenever AWS Marketplace send in new data it gets sent to our bucket ==>OUTPUT : S3 Bucket URL - KMS Key ARN - KMS Key ID - Lambda Role ARN!!
##### Note: After the stack gets deployed Into the tenant AWS account all we need to finish the sync with our bucket is the Lambda Role ARN : that we add to our bucket policy to allow for the sync
