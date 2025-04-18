# 2110_AWS_AD_Project

## Section 1: Project Description

The project focuses on setting up a secure and cost-effective Active Directory solution using AWS services. The primary goal is to integrate AWS IAM Identity Center (SSO), AWS Managed Microsoft AD, EC2 login with Active Directory, and secure S3 bucket access with AD groups. Additionally, AWS SNS and SQS will be implemented for event notifications and login event handling.

## Section 2: Overview

The project will utilize AWS services within the Free Tier where possible, ensuring efficient resource management. The key services involved include:

- **VPC Configuration**: Private and public subnets with NAT Gateway and Internet Gateway.
- **AWS Managed Microsoft AD**: User authentication and access control.
- **EC2 Integration**: Allowing EC2 instances to join the AD domain.
- **S3 Access Control**: Restricting bucket access using AD groups.
- **SNS & SQS**: Managing AD login events and notifications.

## Section 3: System Architecture

The system architecture consists of:

- **VPC with multiple subnets**:
  - Public Subnets: Hosting NAT Gateway and Internet Gateway.
  - Private Subnets: Hosting AWS Managed Microsoft AD and EC2 instances.
- **AWS Directory Service (AWS Managed Microsoft AD)**: Provides authentication and directory services.
- **IAM Identity Center (SSO)**: Centralized user access management.
- **AWS SNS & SQS**: Handling notifications and login event processing.
- **EC2 Instances**: Connecting to AD for domain-joined authentication.
- **S3 Buckets**: Configured with AD group-based access policies.

## Section 4: Data Dictionary

| Data Element     | Description                                   | Type   |
| --------------- | -------------------------------------------- | ------ |
| UserID          | Unique identifier for users in AD            | String |
| GroupID         | Identifier for AD user groups                | String |
| InstanceID      | EC2 instance identifier                      | String |
| S3Bucket    | Name of S3 bucket for AD access control      | String |
| EventID         | Unique event identifier for login events     | String |
| NotificationType | Type of SNS notification (login, alert, etc.) | String |

## Section 5: Data Design

- **User Authentication**: Stored in AWS Managed Microsoft AD with group-based permissions.
- **EC2 Domain Integration**: Using Active Directory credentials to log in.
- **S3 Permissions**: Managed through AD groups for restricted access.
- **Event Logging**: AWS SQS queues store login events for monitoring.
- **Notifications**: AWS SNS publishes alerts on login activities.

## Section 6: User Interface Design

- **AWS Console UI**: Configuring and managing AD, EC2, S3, and IAM.
- **EC2 Instance Login**: Users authenticate using AD credentials.
- **S3 Access Control**: UI for managing bucket permissions via AD groups.
- **SNS & SQS Dashboard**: Monitoring notifications and event queues.

