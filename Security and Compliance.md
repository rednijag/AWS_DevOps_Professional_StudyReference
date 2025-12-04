# Security and Compliance  

1. Object `ETag` is the MD5 Checksum for the object in an S3 bucket, compare it with the original object's checksum to verify object integrity.  

2. AWS Config is one of the most important service for this section, it has more than 70 AWS managed rules and custom rules can be defined using a Lambda function, it can trigger a notification in SNS as a result.  

3. Since AWS Config is used to track and monitor compliance over time, for auto-remediation Use SSM Automation.  

4. Use AWS Config Aggregators to centralize rule creation, observability and compliance across multiple AWS accounts.  

5. The payer account (Management account) of an organization can turn off Reserved Instance (RI) discount and Savings Plans discount sharing for any accounts in that organization, including the payer account.  

6. Service Control Policies are applied at Account or OU level in an Organization (to all users and roles in them) to restrict use of AWS services.  

7. AWS IAM Identity Center provides SSO for all your AWS Organization accounts (Supports Microsoft AD, Onelogin etc) and to your 3rd party Apps. Users and groups in the External Idp should be same in AWS IAM Identity Center.  
 
8. ABAC: Attribute based Access control, use Resource tags on both user/groups and resource policies to allow/deny access.  

9. AWS Firewall Manager can track and manage all ALBs with/without Firewall and auto-remediate based on the applied policies.  

10. AWS Inspector needs running EC2 Instance to check and detect OS level vulnerabilities etc. , So it works in conjunction with Lambda function to create a Patched Golden AMI.  

11. Service Control Policies work only with AWS Organization with full features mode enabled, without an explicit `Allow` for a particular service for a particular account or OU, it denies the service availability, and any `Deny` from the Root level OU to the Account is taken as a `Deny` for that particular service to the particular Account/OU.  
