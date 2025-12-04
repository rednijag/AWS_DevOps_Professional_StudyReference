# Monitoring and Logging  

1. CloudWatch logs agent can't directly send logs to s3, to deliver the logs to s3 create a subscription filter on the CW logs log group and stream it to kinesis data firehose which then delivers it to s3, this setup works similarly when aggregating Cloudwatch Logs from multiple AWS accounts to a Central AWS account (added cross account permissions)

2. Services like vpc flow logs, Cloudfront access logs, ELB access logs can deliver logs directly to s3.  

3. Important Cloudwatch features to keep in mind: Cloudwatch Anomaly detection, Cloudwatch Logs Insight and Cloudwatch Live tail.  

4. Service quota thresholds can trigger cloudwatch alarms, this can be a selective and cheaper alternative to AWS Trusted Advisor.  

5. AWS Procstat plugin for Unified cloudwatch agent is useful when you need to track process level metrics within an EC2 instance.  

6. Lambda extensions provide enhanced observability, metric and log collection for lambda functions, it can send logs and metrics to Cloudwatch as well as other 3rd party applications, It can be either internal (run with the lambda app code itself) or external (runs outside of its scope of execution, thereby a choice for situations where tracing and tracking is needed beyond the scope of execution of the lambda code).  

7. Cloudwatch Logs can send log to (native support) Kinesis Data Streams, Kinesis Firehose, Lambda, S3 and Amazon Opensearch.  

8. Recovering Instance from an CW alarm and the ability to send SNS notifications are two important features of CW alarm.  

9. Alarms can be created over Cloudwatch Log metrics.  

10. Amazon Athena is used for cheaper analysis of Cloudwatch Logs on S3, To Improve performance of Amazon Athena queries use larger file sizes, columnar data and compress data.  


 
