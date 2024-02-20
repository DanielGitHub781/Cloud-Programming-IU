# Setting Up a Static Website on AWS with Terraform: S3 & CloudFront

Welcome to this Terraform project designed to deploy a static website on AWS using S3 for storage and CloudFront for content delivery. Below, you'll find detailed instructions to set up and manage your website infrastructure.

## Prerequisites

Ensure you have the following prerequisites ready:

1. AWS Account: You'll need an AWS account with the necessary permissions to create resources such as S3 buckets, CloudFront distributions, IAM users, Route 53 and IAM policies.

2. Terraform Installed: Make sure Terraform is installed on your local machine or use Docker for easy setup. You can download Terraform from [here](https://www.terraform.io/downloads.html).

## Instructions

Follow these steps meticulously to deploy and manage your website infrastructure:

1. **Creating an IAM User**:

   - Start by creating an IAM user in your AWS account, and let's name it `tf_s3_cloudfront`.
   - Next, attach the `terraform-static-web-site-s3-cloudfront` policy to this user. You'll find the policy JSON content in this repository.

2. **Generating AWS Access Keys**:

   - Proceed to generate an AWS access key and secret access key for the `tf_s3_cloudfront` IAM user.
   - It's crucial to keep these credentials secure, as they grant access to your AWS account.

3. **Configuring AWS Credentials**:

   - Configure your AWS credentials using one of the following methods:
     - **Option 1: Environment Variables**: Set the `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` environment variables with the corresponding access key and secret access key values.
     - **Option 2: Modifying `variables.tf`**: Replace the default values of `aws_access_key_id` and `aws_secret_access_key` in the `variables.tf` file with your access key and secret access key. **Note**: Remember not to expose these credentials publicly.

4. **Initializing Terraform**:

   - Initialize the Terraform environment by running `terraform init`.

5. **Planning the Deployment**:

   - Use `terraform plan` to preview the changes Terraform will apply, ensuring everything aligns with your expectations.

6. **Applying the Configuration**:

   - Finally, execute `terraform apply` to create the website infrastructure. If you want to skip the "yes/no" prompt, you can use `terraform apply -auto-approve`.
