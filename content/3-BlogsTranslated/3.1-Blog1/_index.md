---
title: "Blog 1"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only, please **do not copy verbatim** for your report including this warning.
{{% /notice %}}

# **Centralized Multi-Account Application Resilience Assessment Using AWS Resilience Hub**

By **Venkata Kommuri**, **Venkata Moparthi**, **Santosh Vallurupalli**, and **Tracy Honeycutt** on 05 AUG 2025 in **Management Tools**

## **Introduction**

As organizations scale their cloud environments across multiple **AWS accounts** and regions, managing and accessing **resilience** becomes increasingly complex. Traditional approaches of evaluating **resilience** separately for each **workload**, account, or region can lead to inefficiencies, inconsistencies, and coverage gaps. This challenge is particularly pronounced in distributed architectures utilizing various **Infrastructure as Code (IaC)** tools like **AWS CloudFormation** and **Terraform**.

**AWS Resilience Hub** addresses these challenges by providing a centralized, managed service for monitoring and assessing **resilience** across multi-account cloud architectures. The service enables organizations to define, track, and enhance application **resilience** through unified oversight in a **centralized hub master account**. Integration with **Amazon Simple Notification System (SNS)** provides real-time **drift detection** notifications, helping maintain robust recovery capabilities across distributed deployments while supporting requirements for low latency, data residency compliance, and strengthened **resilience** against disruptions.

## **Understanding AWS Resilience Hub**

**AWS Resilience Hub** is a central location in the **AWS console** for you to manage and improve the **resilience posture** of your applications on **AWS**. **AWS Resilience Hub** enables you to define your resilience goals, assess your **resilience posture** against those goals, and implement recommendations for improvement based on the **AWS Well-Architected Framework**.

**Resiliency** can be defined in terms of metrics called **RTO (Recovery Time Objective)** and **RPO (Recovery Point Objective)**. **RTO** is a measure of how quickly your application can recover after an outage and **RPO** is a measure of the maximum amount of data loss that your application can tolerate. **AWS Resilience Hub** offers a unified view of an application's **resilience posture**, identifies potential risks and provides actionable recommendations to enhance robustness against disruptions. By aligning with the **AWS Well-Architected Framework's** best practices, **Resilience Hub** ensures that the applications can withstand and recover from various failure scenarios.

## **Challenges with Disaggregated Resilience Assessments**

Below outlined are some of the key challenges in detail with disaggregated assessment approach:

### **Fragmented Resilience Evaluations**
Organizations managing **workloads** across multiple **AWS accounts** often conduct **resilience assessments** independently, leading to inconsistencies in evaluation criteria and risk identifications.
Without a unified view, teams may struggle to correlate **resilience** findings across **workloads** leading to blind spots in overall application **resilience**.

### **Lack of Standardized Resilience Policies**
Without standardized **resilience policies**, different teams may define availability targets, **RTO** and **RPO** differently.
This inconsistency can lead to misalignment between business continuity planning, and actual cloud infrastructure capabilities.

### **Difficulty in Data Aggregation**
Aggregating **resilience** data from disparate sources poses another significant challenge. Without a unified platform, administrators must manually compile details of the infrastructure deployed from tools like **AWS CloudFormation** or **Terraform state** files across **Regions** and **accounts**.
This labor-intensive process can introduce errors and delays, making it harder to spot failure points spanning multiple **accounts**, thus prolonging exposure to potential disruptions.

In this blog post, we will explore an architecture that addresses the challenges discussed above. This architecture will help you conduct **resilience assessments** for applications deployed across multiple **AWS accounts** and **Regions**.

## **Prerequisites**

- An **AWS Account**
- **AWS CloudFormation** templates or **Terraform** files defining your applications
- Pre-defined **Recovery Time Objective (RTO)** and **Recovery Point Objective (RPO)** guidelines as per your business requirements

## **Solution Architecture**

The **AWS Resilience Hub Solution** employs a **hub and spoke model** to deliver centralized **resilience** management across an **AWS** environment, enabling organizations to assess and enhance application **resilience** effectively. This solution operates through a **central AWS hub account**, which acts as the administrative focal point for defining **resilience policies**, managing assessments, overseeing Applications across connected **spoke accounts**. The **hub account** connects to multiple **spoke accounts** through **IAM roles** and **trust relationships**. These **spoke accounts** contain the **workloads** and resources that need **resilience** evaluation.

**AWS Resilience Hub** requires two **IAM roles** for secure **cross-account resilience assessment**. The primary role **AWSResilienceHubAssessmentRole** in the **hub account** manages assessment operations, while the secondary role **AWSResilienceHubCrossAccountRole** in **spoke accounts** executes **workload** evaluations. The **hub account's** assessment role orchestrates **resilience assessments** by managing configurations, assuming **cross-account roles**, and coordinating **workload** evaluations.

Customers can leverage **AWS Resilience Hub's drift detection** capabilities to automatically assess their **workloads** on a daily basis. This assessment occurs once every 24 hours. For enhanced monitoring and response, customers have the option to integrate these **drift detection** assessment results with an **SNS topic**. By doing so, relevant teams can subscribe to these notifications, allowing them to receive timely alerts and take corrective actions promptly when deviations are detected. This integration enables a proactive approach to maintaining application **resilience** and ensures that any changes affecting the **resilience posture** are addressed swiftly.



![AWS Resilience Hub Architecture](/images/3-BlogsTranslated/blog1/1.png)
*Fig 1 – Architectural diagram of the solution centralizes Multi-Account Application Resilience Assessment Using AWS Resilience Hub*

## **Key Components of the Solution**

Below are the building blocks of the solution:

### **Central Hub Account**
Serves as the administrative center for **AWS Resilience Hub** where administrators can manage **resilience policies**, view assessment results, coordinate **resilience** strategies across multiple accounts and applications. This account also includes a **SNS topic** that receives **drift** notifications, enabling real-time alerts for subscribed users.

### **Spoke Accounts**
Contain the **workloads** and resources evaluated by **AWS Resilience Hub**, connecting to the **central hub account** through the **IAM roles** and **trust relationships** to enable **resilience assessments**.

### **IAM Roles**

#### **AWSResilienceHubAssessmentRole**
Resides in the **central hub account**; Manages overall configurations, creates **resilience policies**, sets up applications for assessments and assumes **cross account roles** in the **spoke accounts** to delegate tasks securely.

#### **AWSResilienceHubCrossAccountRole**
Located in **spoke accounts**; performs **workload assessments**, executes resource level operations, and reports findings back to the **hub's admin role**, ensuring detailed **resilience** evaluation.

### **Trust Relationships**
Enable the admin role in the **hub account** to delegate tasks to the executor role in **spoke accounts**, maintaining a clear separation of duties while facilitating efficient **resilience** management and assessment across the **AWS** environments.

## **Getting Started**

### **Download the necessary CloudFormation files**
```bash
wget \
https://d2908q01vomqb2.cloudfront.net/artifacts/MTBlog/cloudops-1962/ard.yaml \
https://d2908q01vomqb2.cloudfront.net/artifacts/MTBlog/cloudops-1962/AWSResilienceHubAssessmentRole.yaml \
https://d2908q01vomqb2.cloudfront.net/artifacts/MTBlog/cloudops-1962/AWSResilienceHubCrossAccountRole.yaml \
https://d2908q01vomqb2.cloudfront.net/artifacts/MTBlog/cloudops-1962/AWSResilienceHubSNSTopic.yaml
```

### **Deploy the IAM Roles for Central Hub Account and Spoke Accounts**

In the **hub account** run the below command:
```bash
aws cloudformation create-stack \
--template-body AWSResilienceHubAssessmentRole.yaml \
--stack-name AWSResilienceHubAssessmentRole \
--capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM
```

In each **spoke account(s)** run below commands:
```bash
aws cloudformation create-stack \
--template-body AWSResilienceHubCrossAccountRole.yaml \
--stack-name AWSResilienceHubCrossAccountRole \
--capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM \
--parameter-overrides AWSResilienceHubAssessmentRoleARN=arn:aws:iam::<hubaccount_number>:role/AWSResilienceHubAssessmentRole
```

### **Create an SNS topic to get notified when the application detects the drift**

This **CloudFormation template** sets up an **SNS topic** with its associated access permissions. The template configures both a new **SNS topic** and establishes the necessary access controls (**Resource Policy**) that define which services and users can interact with the **topic**. Specifically, this configuration allows **AWS Resilience Hub** to send notifications about **drift detection** assessment results to the **SNS topic**, helping monitor changes in your **resilience policies**.

```bash
aws cloudformation create-stack \
--template-body AWSResilienceHubSNStopic.yaml \
--stack-name AWSResilienceHubSNSTopic \
--capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM \
--parameter-overrides TopicName=dev-sample-topic EmailAddress=<Enter_Email_Address_of_Recipeint>
```

### **Deploy Sample Workload in Spoke Account**
```bash
aws cloudformation create-stack \
--template-body ard.yaml \
--stack-name resilience-hub-workloads \
--capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM
```

Copy the **ARN** of the **CloudFormation Stack** that was just launched for later use:
```bash
aws cloudformation describe-stacks --stack-name resilience-hub-workloads --query "Stacks[0].StackId" --output text
```

To illustrate the functionality of **cross-account workload assessment** using **Resilience Hub**, we will deploy a sample **workload** in a **Spoke account** and analyze its assessment results from a **Central Account**. The sample application we'll use features a **three-tier architecture** with services deployed into a single **AZ** wherever applicable, comprising an **Amazon CloudFront** for content delivery and caching, **Amazon Simple Storage Service (Amazon S3)** bucket for object storage, an **Amazon Elastic Compute Cloud (Amazon EC2)** instance serving as a web server, and an **Amazon Relational Database Service (Amazon RDS)** instance for database operations. The core objective of this blog post is to demonstrate how **Resilience Hub** assesses the **resilience** of this architecture and to explore how we can enhance it based on the recommendations provided by the tools. Please note that the sample architecture does not follow **AWS best practices** and is used here to demonstrate how **AWS Resilience Hub** identifies **resiliency gaps** and generates recommendations for improvements.



![Three-tier Workload Architecture](/images/3-BlogsTranslated/blog1/2.png)

*Fig 2 – Architectural diagram of sample three-tier workload*

## **Setting Up Centralized Resilience Assessment in the Hub Account**

To start, login to the **AWS hub account** and navigate to the **AWS Management Console**.

1. Select **AWS Resilience Hub** and select **Add application** → **Get started**, choose **Add application**.

2. Select **Add Application** under **Resilience management**.
![Add Application](/images/3-BlogsTranslated/blog1/3.png)


3. Enter application details and select **Resource collection**.
![Resilience Management](/images/3-BlogsTranslated/blog1/4.png)


1. Add the **AWS CloudFormation stack ARN** of your sample **workload** that you have copied from Step 3 above (Deploy Sample Workload in Spoke Account).

![CloudFormation Stack ARN](/images/3-BlogsTranslated/blog1/5.png)

5. Define the new **resilience policy** for the **workload**. For this sample **workload**, we will set "**MissionCritical**" policy with **RTO** and **RPO** set to 10 minutes and 4 minutes. If you already have pre-defined **Resiliency Policies** defined in your account, you can choose to use them by checking the option "Choose an existing resiliency policy".

![Resilience Policy](/images/3-BlogsTranslated/blog1/6.png)

6. For **multi-account assessment**, select **AWSResilienceAssessmentRole** from drop down and under **Add cross account IAM role(s) ARN**, add the **ARN** for **AWSResilienceCrossAccountRole** from the **spoke account(s)**.

   **Note:** If deploying **workloads** across multiple **spoke accounts**, add the **AWSResilienceCrossAccountRole ARN** from each **spoke account** to enable **cross-account resilience** capabilities.

![Multi-Account Assessment](/images/3-BlogsTranslated/blog1/7.png)

7. By selecting the "**Automatically assess daily**" option, you can set up daily automated evaluations of your **workloads** specified in **CloudFormation** and **Terraform templates**. Additionally, you have the option to receive email notifications through your subscribed **SNS topic**. These notifications will inform you of any **drift detection** assessment results, alerting you to changes in your applications' **resilience posture** over time. Checkbox the "**Get Notified when the application drifts**" and select the **SNS topic** that is created in Step 2.

![Daily Assessment Configuration](/images/3-BlogsTranslated/blog1/8.png)

8. Now, select **Add application**.

![Add Application Button](/images/3-BlogsTranslated/blog1/9.png)

9. Once the application is successfully imported from **AWS CloudFormation template**, select **Publish application**.

![Publish Application](/images/3-BlogsTranslated/blog1/10.png)

10. After publishing your application, it is now ready for assessment.



## **Running a Resilience Assessment**

1. Navigate to the **Resources** tab to view deployed components from the **AWS CloudFormation template** for sample **workload** in **spoke account**. Now, you can select **Assess application** to start the application assessment.

![Resources Tab](/images/3-BlogsTranslated/blog1/11.png)

2. Name your assessment report and select **Run**.

![Assessment Report Name](/images/3-BlogsTranslated/blog1/12.png)

3. The assessment status will be **in progress** and will finish the assessment in a few minutes.

![Assessment In Progress](/images/3-BlogsTranslated/blog1/13.png)

## **Reviewing the Resilience Assessment**

Once the assessment is completed, the report is generated for review.

![Assessment Completed](/images/3-BlogsTranslated/blog1/14.png)

1. You can find assessment reports of your application in the **Assessments** section of your application.
2. In the left navigation menu, choose **Applications**.
3. In **Applications**, open an application.
4. In **Assessments** tab, choose an assessment report from the **Resiliency assessments** section.

When you open the report, you see the following:
- An overall overview of the assessment report
- Recommendations to improve **resiliency**
- Recommendations to set up alarms, **Standard Operating Procedures (SOPs)**, and tests

![Assessment Report Overview](/images/3-BlogsTranslated/blog1/15.png)

Upon examining the report above, you'll observe that the "**Current Policy Compliance**" section indicates that the existing infrastructure falls short of meeting the **Recovery Time Objective (RTO)** and **Recovery Point Objective (RPO)** defined in your **resilience policy**. To address this, **AWS Resilience Hub** offers valuable recommendations, enabling you to implement corrective measures and enhance your application's **resilience** to align with your established objectives. For instance, selecting the **RDS AppComponent** will reveal a detailed set of recommendation assessments, as illustrated in the following image.

![Policy Compliance](/images/3-BlogsTranslated/blog1/16.png)



With these **resilience** recommendations in hand, application and infrastructure teams can now implement appropriate changes to their systems, enhancing their ability to withstand unexpected failures. This process demonstrates the power of **AWS Resilience Hub's cross-account** functionality—while the sample **workload** is deployed in a **spoke account**, the assessment is conducted in the **central hub account**. This centralized approach allows for consolidated assessment reports to be available in the **central hub account**, providing a comprehensive view of **resilience** across multiple accounts and applications. This centralized oversight enables organizations to maintain consistent **resilience** standards and efficiently manage their **multi-account AWS** environments.



## **Conclusion**

The solution provides a centralized approach to assessing and improving **workload resilience** across multiple **AWS accounts** and regions, which is critical for maintaining business continuity and meeting business requirements. It integrates seamlessly with applications deployed via **AWS CloudFormation** and **Terraform** deployments, utilizing a **hub and spoke model** that enables organizations to efficiently evaluate **resilience postures** while maintaining security through **IAM Role-based** access controls. 

The ability to assess stacks deployed outside of the **AWS region** of the **central hub account**, combined with **cross-account IAM roles** integration, enhances the service's effectiveness by allowing organizations to gain visibility into global **workloads** and ensure secure, scalable assessments. By adopting **AWS Resilience Hub**, organizations can transform **resilience** management from a reactive process into a proactive strategy, leveraging automated assessments, detailed recommendations, and clear **resilience** metrics to build fault-tolerant, highly available applications that align with best practices for disaster recovery and operational **resilience**, making it an essential tool for maintaining a **resilient**, **well-architected AWS** environment as cloud infrastructures grow in complexity. 

To get started with implementing this solution in your organization, download the **CloudFormation templates** provided in this post and follow our step-by-step deployment guide in the **AWS Resilience Hub** documentation. You can also explore additional **resilience** assessment strategies through the **AWS Well-Architected Framework**.

## **Authors Bio**

**TAGS:** **AWS Resilience Hub**, **Resiliency**

### **Venkata Kommuri**
**Venkata Kommuri**, an **Infrastructure Architect** at **AWS**, specializes in designing and implementing complex cloud solutions across commercial and **GovCloud** environments. His expertise spans **cloud migrations**, **containerization**, **networking**, and **Generative AI** deployments, delivering scalable and secure enterprise architectures that drive digital transformation while maintaining operational excellence.
![Authors](/images/3-BlogsTranslated/blog1/17.png)
### **Venkata Moparthi**
**Venkata Moparthi** is a **Senior Solutions Architect** at **AWS**, specializing in **cloud migrations**, **generative AI**, and **resilience**. As a trusted technology leader, he architects transformative cloud solutions for **financial services** and cross-industry enterprises, consistently delivering optimized outcomes that align technical innovation with business objectives.
![Authors](/images/3-BlogsTranslated/blog1/18.png)
### **Santosh Vallurupalli**
**Santosh Vallurupalli** is a **Sr. Solutions Architect** at **AWS**. **Santosh** specializes in **networking**, **containers**, and **migrations** and enjoys helping customers in their journey of cloud adoption and building **cloud native** solutions for challenging issues.
![Authors](/images/3-BlogsTranslated/blog1/19.png)
### **Tracy Honeycutt**
**Tracy Honeycutt** is a **Solutions Architecture Manager** based in Atlanta, GA. **Tracy** is focused on guiding **Financial Services Industry (FSI)** customers through their cloud journeys, accelerating **migrations**, modernizing **workloads**, and adopting new ways of working. **Tracy** has a specialty in **networking** and is passionate about **networking**, **DNS**, and helping customers who are early in their cloud journeys.
![Authors](/images/3-BlogsTranslated/blog1/20.png)