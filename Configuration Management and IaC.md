# Configuration Management and IaC  

1. Updating a nested stack doesn't automatically trigger a new Parent stack deployment.  

2. Cross-stack reference is used to describe CFT Stacks that Import resourceIDs and values provided from the designated export output section of other stacks. The export names must be unique for your AWS account and can be used only within the same region.  

3. Nested stacks are chosen for modularity and brevity in your CFT whereas Cross stack references are ideally used to reference values of pre-created components required to be referenced in your current stack. For example: VPCs created by a Networking team needs to be referenced in your CFT to deploy your EC2 instances.  

4. Stack policies can help prevent stack resources from being unintentionally updated or deleted during a stack update and is not to be confused with an Access Policy like IAM used for permissions.  

5. cfn-hup is a daemon that can run in an EC2 instance that polls the Cloudformation API to detect changes in the instance metadata and can apply configurations as directed.  

6.