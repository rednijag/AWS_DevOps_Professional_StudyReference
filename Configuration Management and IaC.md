# Configuration Management and IaC  

1. Updating a nested stack doesn't automatically trigger a new Parent stack deployment.  

2. Cross-stack reference is used to describe CFT Stacks that Import resourceIDs and values provided from the designated export output section of other stacks. The export names must be unique for your AWS account and can be used only within the same region.  

3. Nested stacks are chosen for modularity and brevity in your CFT whereas Cross stack references are ideally used to reference values of pre-created components required to be referenced in your current stack. For example: VPCs created by a Networking team needs to be referenced in your CFT to deploy your EC2 instances.  

4. Stack policies can help prevent stack resources from being unintentionally updated or deleted during a stack update and is not to be confused with an Access Policy like IAM used for permissions.  

5. cfn-hup is a daemon that can run in an EC2 instance that polls the Cloudformation API to detect changes in the instance metadata and can apply configurations as directed.  

6. Most Important Cloudformation attributes , CreationPolicy, UpdatePolicy, ReplacePolicy.  

7. If the Cloudformation service isn't assigned permissions using the service role then it uses the permissions of the IAM user triggering it, provided the user has `iam:PassRole` Permission.   

8. Custom resources in CFT are not supported for drift detection.  

9. When using CFT for creating/updating IAM resources, `capability_Named_IAM` and `capability_IAM` are needed.  

10. Cloudformation Hooks provide a way to proactively check and validate any CFT before it creates or updates any resources. For example a Lambda based hook can check whether the CFT is creating only encrypted EBS or not.  

11. The `aws-controltower-AllConfigNotifications` SNS topic receives all events published by AWS Config. For example, this topic informs you if a control violation has occurred. It also gives information about other types of events.  

12. AWS WAF supports Country,IP based blocking and Captchas as well, So AWS WAF can also be used for Geo-restriction.  

13. AWS WCU are the WAF Capacity Units which are consumed based on the resources each rule consumes, a rule group cant have more than 5000 WCUs. Also the maximum number of headers that can be sent to WAF is 200.  
 
14. 



