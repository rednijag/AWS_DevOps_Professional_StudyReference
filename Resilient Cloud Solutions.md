# Resilient Cloud Solutions  

1. Aliases targeting different versions of AWS lambda with weighted traffic distribution enable canary deployment. Aliases have unique ARN which is used to target them individually (similar to an http endpoint for api).  

2. Reserved Concurrency for a lambda function is the maximum threshold it can scale to whereas provisioned concurrency is the compute power available to it from the get go.  

3. If a lambda function is throttled it returns the request to an internal queue which it tries later again when free till the next 6 hours.  

4. Lambda can use EFS if running in a VPC along with ephemeral storage and /tmp.  

5. All aws apis(s3 api, cloudwatch api)  can be exposed through AWS API Gateway for better control, safety and ease of use.  

6. Each deployed stage (changes the url path) can have its own personal variables called stage variables which can be used to modify its behavior.  

7. API gateway has a response cache which can be reset using header (make sure to setup authentication on the cache control).  

8. AWS Fargate based ECS and EKS are more resilient when compared to EC2 based ones as the scaling configuration etc. is managed by AWS itself.  

9. ECS task role for permissions and access is defined in ECS Task definition.  

10. ECS task events are logged in event bus, which can be used to trigger SNS and alarms.  

11. ECS logging using awslogs driver (in task definition), EC2 based ecs needs ecs cloudwatch agent or a sidecar container can be used just to capture and push logs to CW.  

12. Global Accelerator optimizes network paths for application traffic to improve performance and availability, especially for non-HTTP and dynamic applications, while CloudFront is a CDN that caches static content at edge locations to speed up delivery to end-users. Use Global Accelerator for applications like gaming, IoT, or services needing static IP addresses and rapid failover; use CloudFront for websites, video streaming, and software distribution where content caching is key.  

13. Lambda managed instances run on EC2 instances of your choosing, the backend ec2 instances lifecycle,OS etc is managed by AWS just like in a normal Lambda function but you get the isolated environment (dedicated EC2 instance in your account) and higher performance (useful for heavier applications/web services).  

14. Lambda functions can be configured to run for more than 900 seconds using durable functions.  

15. Lambda functions can be accessed from a vpc internally using vpc endpoints, to secure the endpoint use an interface endpoint policy  for lambda.  

16. Lambda can have a dedicated function url which can also be used to stream responses to client (bigger sized responses upto 200 mb, lesser latency to client as its streamed as and when created).  

17. Lambda Layers provide a way to bundle up your dependencies and non core functionalities outside of the base code for your lambda thereby decreasing the deployment package size and giving you the ability to share these layers with other lambda functions that might need it.  

18. Auto migrate EC2 Instance based DB to RDS using Amazon DMS.  

19. RDS proxy is a good when you are using any application that opens a lot of connections with the DB that could overwhelm its connection pools, or when a DB is serving Lambda functions as they open/close connections frequently.  

20. RDS Read replicas can be Multi-AZ and Mult-Region whereas RDS Standby DB instances are only Multi-AZ. Standby DB is auto-promoted whereas read replicas need to be promoted to master manually.  




