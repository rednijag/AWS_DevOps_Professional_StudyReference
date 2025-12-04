# Incident and Event Response  

1. Most events happening with AWS resources are logged in Event bus, Also supports Partner Event buses for some 3rd party applications like datadog.  

2. AWS Account health Dashboard (For your AWS account's AWS services) vs. AWS Services Health Dashboard (general view of all AWS Service health).  

3. Can aggregate all AWS Account health dashboard information in a single AWS Organisation account and trigger Event bridge events to trigger a notification in SNS, from there the world is your oyster.  

4. For EC2 Instances, System Status check + Instance Status Check = Combined Status Check.  

5. CloudTrail logs management events (For ex. CreateIAMpolicy, AttachIAMPolicy) by default but doesn't log data events(S3PutObject etc) as they are data intensive, but the latter can be turned on.  

6. Cloudtrail Insights just like Cloudwatch Insights, detect unusual activity in their respective logs.  

7. Create EventBridge events on any ClouTrail event basically all API calls that your Cloudtrail is logging (Management, Data and Insight).  

8. Amazon X-ray is useful in debugging application level errors as it is a native AWS APM that also provides visual analysis of the workflow, the daemon needs to be installed in EC2, ECS etc with respective permissions to send out data to the X-ray service.  

9. RDS standby is only available within the same region whereas read-replicas can be in a different region and can be promoted to master manually incase of a DR scenario.  

