# CD
This repo contains ci/cd pipeline with AWS CodeBuild. I've implemented this pipeline with hugo template on aws.

##### Difference between Continuous Integration, Delivery, Deployment
<img src = "https://www.saviantconsulting.com/images/blog/continuous-integration-continuous-delivery-and-continuous-deployment.gif">

---

#### Few AWS services related to CI/CD
- **AWS CodeCommit** – ```A fully-managed source control service that hosts secure Git-based repositories```. CodeCommit makes it easy for teams to collaborate on code in a secure and highly scalable ecosystem. This solution uses CodeCommit to create a repository to store the application and deployment codes.
- **AWS CodeBuild** – ```A fully managed continuous integration service that compiles source code, runs tests, and produces software packages that are ready to deploy, on a dynamically created build server.``` This solution uses CodeBuild to build and test the code, which we deploy later.
- **AWS CodeDeploy** – ```A fully managed deployment service that automates software deployments to a variety of compute services such as Amazon EC2, AWS Fargate, AWS Lambda, and your on-premises servers.``` This solution uses CodeDeploy to deploy the code or application onto a set of EC2 instances running CodeDeploy agents.
- **WS CodePipeline** – ```A fully managed continuous delivery service that helps you automate your release pipelines for fast and reliable application and infrastructure updates.``` This solution uses CodePipeline to create an end-to-end pipeline that fetches the application code from CodeCommit, builds and tests using CodeBuild, and finally deploys using CodeDeploy.
- **AWS CloudWatch Events** – ```An AWS CloudWatch Events rule is created to trigger the CodePipeline on a Git commit to the CodeCommit repository.```
- **Amazon Simple Storage Service (Amazon S3)** – ```An object storage service that offers industry-leading scalability, data availability, security, and performance.``` This solution uses an S3 bucket to store the build and deployment artifacts created during the pipeline run.
- **AWS Key Management Service (AWS KMS)** – ```AWS KMS makes it easy for you to create and manage cryptographic keys and control their use across a wide range of AWS services and in your applications.``` This solution uses AWS KMS to make sure that the build and deployment artifacts stored on the S3 bucket are encrypted at rest.

To unzip the tar.gz use this 
```
tar xzvf hugo_0.99.1_Linux-32bit.tar.gz
````
[Hugo](https://github.com/gohugoio/hugo/releases)
##### [Resource](https://noahgift.github.io/cloud-data-analysis-at-scale/topics/continuous-delivery.html)
##### [YAML](https://circleci.com/blog/what-is-yaml-a-beginner-s-guide/) / [YAML Documentation](https://yaml.org/spec/1.2.2/)
