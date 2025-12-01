# Monitoring and Logging  

1. CloudWatch logs agent can't directly send logs to s3, to deliver the logs to s3 create a subscription filter on the CW logs log group and stream it to kinesis data firehose which then delivers it to s3.  

2. Services like vpc flow logs, Cloudfront access logs, ELB access logs can deliver logs directly to s3.  

3. Important Cloudwatch features to keep in mind: Cloudwatch Anomaly detection, Cloudwatch Logs Insight and Cloudwatch Live tail.  

4. Service quota thresholds can trigger cloudwatch alarms, this can be a selective and cheaper alternative to AWS Trusted Advisor.  

5. AWS Procstat plugin for Unified cloudwatch agent is useful when you need to track process level metrics within an EC2 instance.  

6. 

