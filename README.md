# AWS-IAM-User-Creation-and-Access-Management-Project
AWS IAM Security Implementation: User Access Control, Policy Management, and MFA Integration
Project Title

AWS IAM Security Implementation: User Access Control, Policy Management, and MFA Integration
Project Index (Table of Contents)

    Introduction to AWS IAM
    AWS Management Console Access
    Creating an IAM User
    Creating an IAM User Group
    Assigning User to Group
    Review and Creating the IAM User
    IAM Password Policy Configuration
    IAM User Login Process
    Accessing AWS Resources using IAM User (Amazon S3)
    Testing IAM User Permissions and Access Restrictions
    Adding Additional Permissions to IAM User (Billing Access)
    Enabling Multi-Factor Authentication (MFA) for IAM User
    Configuring Google Authenticator for MFA
    Security Best Practices Implemented
    Project Outcome and Learning Summary

1. Introduction

Identity and access management (IAM) is a service provided by ** that enables secure management of users, permissions, and access to AWS resources.
Press enter or click to view image in full size
AWS DASHBOARD

Using IAM, administrators can:

    Create users
    Organize users into groups
    Assign policies (permissions)
    Control access to AWS services like

This project demonstrates how to create an IAM user, assign permissions through a group, and allow the user to access AWS resources securely.
2. AWS Console Access

First, login to the AWS Management Console.

From the AWS console:

Open Services

Search for IAM

Click IAM Dashboard

The IAM dashboard displays:

    Security recommendations
    IAM resources (Users, Groups, Roles, Policies)
    Account security information

Press enter or click to view image in full size
console
3. Creating an IAM User

Next step is creating a new IAM user.

Steps:

    Open IAM
    Click Users
    Click Create User

Press enter or click to view image in full size

Enter :

    User name: kalyan
    Enable AWS Management Console access
    Password type: Auto generated
    Require password reset: Yes

This ensures secure access for the new user.
4. Creating a User Group

Instead of attaching permissions directly to a user, AWS recommends using groups.

Steps:

    Click Create Group
    Enter group name

Press enter or click to view image in full size
Press enter or click to view image in full size

Then select the policy:

AmazonS3FullAccess

This policy allows full access to S3 buckets.
5. Assign User to Group

Next:

    Add the user kalyan
    Assign the group kalyangroup

This automatically gives the user S3 permissions through the group policy.

This follows the AWS best practice of role-based access control.
6. Review and Create User

Before creating the user, review the configuration.

Details include:

    Username: kalyan
    Password type: Auto-generated
    Permissions: ABC

Once verified, click:

Create User

The user is successfully created.
Press enter or click to view image in full size
USER CREATED SUCCESFULLY
7. Password Policy Configuration

To improve security, configure the IAM password policy.
Press enter or click to view image in full size
PASSWORD POLICY

Configured settings:

    Minimum length: 8 characters
    Require uppercase
    Require lowercase
    Require numbers
    Require special characters
    Password expiration: 90 days
    Prevent password reuse

This improves account security.
8. IAM User Login

The newly created user logs in using the IAM user login URL.
Download the Medium App

Steps:

    Open IAM login page
    Select IAM User
    Enter:

Account ID
Username
Password
Press enter or click to view image in full size
ACCOUNT ID
Press enter or click to view image in full size
USERNAME & PASSWORD
Press enter or click to view image in full size
PASSWORD RESET

During the first login:

    The user is required to change the password.

9. Accessing AWS Resources

After login, the IAM user can access resources permitted by the policy.

Example:

Access Amazon S3

The user can:

    Create buckets
    Upload files
    Manage objects

Press enter or click to view image in full size
CREATING S3 BUCKET

This confirms that the S3 access policy is working correctly.
10. Testing IAM User Permissions

After creating the IAM user kalyan and assigning only Amazon S3 Full Access, the user logged into the AWS console.

However, the user does not have permission to access other AWS services.

Example services that are restricted:

    Amazon EC2
    Amazon VPC
    Amazon RDS
    AWS Billing and Cost Management

Because the IAM user has only S3 permissions, accessing other services results in Access Denied errors.
Press enter or click to view image in full size
Press enter or click to view image in full size
EC2
Press enter or click to view image in full size
RDS
Press enter or click to view image in full size
BILLING AND COST MANAGEMENT

Example errors observed:

    iam:GetAccountSummary Access Denied
    ec2 API Error
    rds:DescribeDBInstances Access Denied
    Billing Access Denied

This demonstrates the principle of least privilege, where a user can only access resources that are explicitly allowed.
11. Adding Additional Permissions to IAM User

To allow access to additional services such as Billing, permissions must be added to the IAM user.

Steps followed:

    Go to IAM
    Click Users
    Select user ABC
    Click Add permissions
    Select Attach policies directly
    Search for billing

Billing (AWS Managed Policy)

After attaching this policy, the user can now access:

    Billing dashboard
    Cost management tools
    Usage reports

This confirms that permissions control access to AWS services.
12. Enabling Multi-Factor Authentication (MFA)

To improve security, MFA was enabled for the IAM user account.

**AWS Identity and Access Management supports MFA to provide an additional security layer during login.

Steps performed:

    Go to IAM
    Select Users
    Choose user ABC
    Click Assign MFA Device

Press enter or click to view image in full size
ASSINGING MFA
Using Google Authenticator for MFA

The **Google Authenticator app was used to configure MFA.

Configuration steps:

    Install Google Authenticator on a mobile device
    Scan the QR code displayed in AWS
    The app generates 6-digit OTP codes
    Enter two consecutive codes in AWS
    Click Assign MFA

Now the IAM user login requires:

    Username
    Password
    MFA verification code

This significantly increases account security.
15. Security Benefits Implemented

The project implemented several AWS security best practices:

✔ IAM user-based access control
✔ Group-based permission management
✔ Policy-based authorization
✔ Least privilege principle
✔ Password policy enforcement
✔ Multi-Factor Authentication (MFA)
16. Final Project Outcome

This project successfully demonstrated:

    Creating IAM users
    Implementing IAM groups
    Assigning policies for resource access
    Restricting services using least privilege principle
    Handling Access Denied errors
    Adding additional permissions when required
    Enforcing password policies
    Implementing Multi-Factor Authentication (MFA)
    Providing controlled and secure access to AWS services.
