---
title: "Week 10 Worklog"
date: 2025-09-09
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---



### Week 10 Objectives:

* Continue developing and perfecting the final course project.
* Integrate API into frontend and resolve CORS issues.
* Migrate from Node.js to Java for Lambda functions.
* Resolve technical errors and optimize deployment.
* Attend AWS Cloud Mastery Series event.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Continue working on project <br>&emsp; + Create API Gateway and integrate Lambda <br>&emsp; + Create IAM Role <br>&emsp; + Create Lambda Function DynamoDB_API_Handler <br> - Create API Gateway and integrate with Lambda <br>&emsp; + Access API Gateway service <br>&emsp; + Create REST API <br>&emsp; + Create Resource, create Method for each table in DynamoDB <br>&emsp; + Attach Lambda to each method <br>&emsp; + Encountered error: The final policy size (20588) is bigger than the limit (20480)                                                                                                   | 10/11/2025 | 10/11/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Continue working on project <br>&emsp; + Go to office to work on project with team members <br>&emsp; + Integrate API into frontend <br>&emsp; + Encountered CORS policy error: No 'Access-Control-Allow-Origin' <br>&emsp; + Fix OPTIONS method to resolve error <br>&emsp; + Fix Lambda <br> - Encountered error: the server responded with a status of 400 <br>&emsp; + Continue fixing code and logic in Lambda                                              | 11/11/2025 | 11/11/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Continue working on project <br>&emsp; + Rewrite Java code from scratch to deploy to Lambda <br>&emsp; + Edit code multiple times to move code from local to Lambda <br>&emsp; + Build JAR file <br>&emsp; + Deploy to Lambda | 12/11/2025 | 12/11/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Continue working on project <br>&emsp; + Encountered ClassNotFoundException error <br>&emsp; + Changed from Spring Cloud Function to aws-serverless-java-container-springboot2 <br>&emsp; + Added maven-shade-plugin <br>&emsp; + Added core and event <br>&emsp; + Successfully resolved the error                            | 13/11/2025 | 13/11/2025      | [Resolving ClassNotFoundException error](https://docs.aws.amazon.com/lambda/latest/dg/java-package.html#java-package-maven) |
| 6   | - Attend AWS Cloud Mastery Series #1 event                                                                                     | 14/11/2025 | 14/11/2025      | [AWS Cloud Mastery Series #1](https://luma.com/imkevnow?tk=0gHFkq) |


### Week 10 Achievements:

* **Continued developing API Gateway and Lambda:**
  * Continued building API Gateway and integrating Lambda
  * Created and configured IAM Role for Lambda functions
  * Deployed Lambda Function DynamoDB_API_Handler
  * Accessed and set up API Gateway service
  * Created REST API and configured endpoints
  * Created Resources and Methods for each table in DynamoDB
  * Attached Lambda functions to each HTTP method
  * Encountered and resolved policy size limit error

* **Team collaboration and frontend integration:**
  * Went to office to work on project with team members
  * Integrated API into frontend application
  * Encountered and resolved CORS policy error: No 'Access-Control-Allow-Origin'
  * Fixed OPTIONS method to resolve CORS error
  * Modified Lambda function to support CORS
  * Encountered "the server responded with a status of 400" error
  * Continued fixing code and logic in Lambda

* **Migration to Java and deployment optimization:**
  * Rewrote Java code from scratch to deploy to Lambda
  * Edited code multiple times to move code from local to Lambda
  * Built JAR file for Java application
  * Deployed Java application to AWS Lambda
  * Understood challenges when migrating programming languages

* **Resolved ClassNotFoundException error:**
  * Encountered ClassNotFoundException error when running Java on Lambda
  * Changed from Spring Cloud Function to aws-serverless-java-container-springboot2
  * Added maven-shade-plugin to Maven configuration
  * Added AWS Lambda core and event dependencies
  * Successfully resolved the error and Lambda runs stably
  * Mastered how to package Java applications for AWS Lambda

* **Attended event and learned:**
  * Attended AWS Cloud Mastery Series #1 event
  * Explored new trends in AWS cloud services
  * Connected with AWS community and shared experiences
  * Updated knowledge about best practices and new features
  * Applied learned knowledge to practical projects
