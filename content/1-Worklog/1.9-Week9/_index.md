---
title: "Week 9 Worklog"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---



### Week 9 Objectives:

* Continue reviewing and consolidating knowledge after the exam.
* Start implementing the final course project with serverless services.
* Set up Lambda Trigger and integrate with S3.
* Build API Gateway and connect with Lambda and DynamoDB.
* Start creating workshop framework for the project.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Continue reviewing exam questions to consolidate knowledge                                                                                                   | 3/11/2025 | 3/11/2025      | [AWS Knowledge Review](https://kananinirav.com/practice-exam/exams.html) |
| 3   | - Start working on project <br>&emsp; + Prepare & Configure Lambda Trigger for S3 <br>&emsp; + Create S3 Bucket <br>&emsp; + Configure Lambda Trigger for S3 <br>&emsp; + Upload CSV data to Bucket                                              | 4/11/2025 | 4/11/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Continue working on project <br>&emsp; + Create API Gateway and integrate Lambda <br>&emsp; + Create IAM Role <br>&emsp; + Create Lambda Function DynamoDB_API_Handler <br> - Create API Gateway and integrate with Lambda <br>&emsp; + Access API Gateway service <br>&emsp; + Create REST API <br>&emsp; + Create Resource, create Method for each table in DynamoDB <br>&emsp; + Attach Lambda to each method <br>&emsp; + Encountered error: The final policy size (20588) is bigger than the limit (20480) | 5/11/2025 | 5/11/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Continue completing API Gateway: <br>&emsp; + Delete old Lambda DynamoDB_API_Handler to remove all old policies and create new DynamoDB_API_Handler with refined code <br>&emsp; + Create new proxy Resource and Method <br>&emsp; + Attach Lambda <br>&emsp; + Enable CORS <br>&emsp; + Deploy API <br>&emsp; + Test API using Postman                            | 6/11/2025 | 6/11/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - After completing API Gateway section: <br>&emsp; + Start creating workshop framework                                                                                     | 7/11/2025 | 7/11/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Week 9 Achievements:

* **Reviewed and consolidated knowledge:**
  * Continued reviewing exam questions to consolidate knowledge
  * Reinforced basic AWS concepts after the exam
  * Identified weak points that need improvement
  * Prepared knowledge for practical project implementation

* **Started project implementation:**
  * Prepared and planned for the final course project
  * Explored serverless architecture and components
  * Identified AWS services needed for the project
  * Designed data flow and architecture

* **Set up Lambda Trigger for S3:**
  * Created and configured S3 Bucket for the project
  * Configured Lambda Trigger to handle S3 events
  * Uploaded CSV data to S3 Bucket
  * Verified trigger functionality and data processing
  * Understood event-driven architecture patterns

* **Built API Gateway and integration:**
  * Created and configured IAM Role for Lambda
  * Wrote and deployed Lambda Function DynamoDB_API_Handler
  * Accessed and set up API Gateway service
  * Created REST API and configured endpoints
  * Created Resources and Methods for each table in DynamoDB
  * Attached Lambda function to each HTTP method

* **Resolved issues and optimization:**
  * Encountered and resolved policy size limit error (20588 > 20480)
  * Deleted old Lambda and created new DynamoDB_API_Handler
  * Optimized code and refined policies
  * Created new proxy Resource and Method
  * Attached Lambda and enabled CORS for API
  * Deployed API and tested using Postman

* **Completed API and prepared workshop:**
  * Completed API Gateway section and verified functionality
  * Started creating workshop framework for the project
  * Prepared documentation and guides
  * Planned next steps
  * Evaluated project progress and quality
