# SDLC Automation

1. CodePipeline, CodeBuild and CodeDeploy all use S3 buckets (generated during usage automatically) to interface and share artifacts with each other, therefore their required service roles should have S3 related permissions.

2. EventBridge is critical when connecting two different Codebuild or Codepipeline , stages or pipelines, as every step of a CodePipeline stage/action or a Codebuild success/failure results in an Event Bridge event which can be used to trigger alternative pathways for example: In case of a failure triggering a lambda function to delete data deployed on S3 buckets before rolling back the deployment using Codebuild/Codepipeline. 

3. CodeDeploy needs CodeDeploy agent to be installed in target EC2 instances unlike for lambda functions, API Gateway and ECS clusters. 

4. CodePipeline has 'runOrder' feature can be used to run build/test etc actions in parallel to reduce the execution time from repository to deployment. 

5. By default CodeDeploy removes all download files from the target instance before doing a fresh deployment, leading to challenges if there are files in the deployment directory that are not part of your repository where the code is published, to bypass this, use the `File exists` behavior to overwrite or retain.

6. Codebuild has jenkins, cloudbees and teamcity plugin features to act as their worker agent.  

7. Codedeploy integration rollback can be triggered based on a Cloudwatch alarm.  

8. During an ECS deployment using CodePipeline Validation tests are to be run on the `AfterAllowTestTraffic` lifecycle hook.  



