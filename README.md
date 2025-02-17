## Automating IAM Resource Creation with AWS CloudFormation

### Overview

This project provides an AWS CloudFormation template to automate the creation of IAM users and related resources. The template defines user groups, assigns permissions, sets up event-driven logging using AWS Lambda, and stores temporary credentials securely.

### Features

- **One-Time Password Generation**: Automatically generates a temporary password for IAM users, stored securely in AWS Secrets Manager.
- **IAM Groups and Permissions**:
  - `S3UserGroup`: Read access to Amazon S3.
  - `EC2UserGroup`: Read access to Amazon EC2.
- **IAM Users**:
  - `s3-user`: Assigned to `S3UserGroup` with temporary login credentials.
  - `ec2-user`: Assigned to `EC2UserGroup` with temporary login credentials.
- **AWS Systems Manager (SSM) Parameter Store**: Stores user email attributes.
- **EventBridge Integration**:
  - Detects new IAM user creation.
  - Triggers an AWS Lambda function to retrieve and log user details.
- **AWS Lambda Logging**:
  - Fetches user email and password.
  - Logs details in Amazon CloudWatch.
