# Resilient Cloud Solutions  

1. Aliases targeting different versions of AWS lambda with weighted traffic distribution enable canary deployment. Aliases have unique arn which is used to target them individually (similar to an http endpoint for api).  

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


