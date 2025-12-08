---
title: "Blog 3"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---



# **Strengthen Your AWS Cloud Storage Security with Superna Defender**

By **Andrew Peng** and **Andrew MacKay** on 07 JUL 2025 in **Amazon FSx**, **Amazon FSx for Windows File Server**, **Amazon Simple Storage Service (S3)**, **AWS Marketplace**, **Partner solutions**, **Software**, **Storage**

*By **Andrew MacKay**, **CTO and Strategy Officer** – **Superna***  
*By **Andrew Peng**, **Sr. Specialist SA**, **FSx for Windows File Server** – **AWS***

## **Introduction**

As customers migrate storage into **Amazon Web Services (AWS)**, protecting file and object storage in the cloud is a security concern. Understanding and implementing a storage framework that includes robust security measures is critical to protect data from **ransomware**, unauthorized access, and exfiltration. Organizations are constantly looking for a solution that can provide protection and monitoring of their cloud based storage.

In this post, we will explore how **Superna Defender** can help to monitor and protect **AWS storage** resources at the object or file level in real-time, by providing the "**who, what, and where**" of every event. **Superna Defender** can provide a solution to help maintain alignment with **Cyberstorage** standards for object and file storage, and can also help to protect, monitor, and restore storage systems.
![Introduction](/images/3-BlogsTranslated/blog3/1.png)
![Introduction](/images/3-BlogsTranslated/blog3/2.png)

## **Malware and ransomware threats to storage**

The threat of **ransomware** and **malware** to cloud storage is becoming increasingly complicated and sophisticated. Affected end user devices with authorized access to network shares can expose a large surface area to threats. Data loss, **ransomware**, and data exfiltration are possible if **Amazon Simple Storage Service (Amazon S3)** buckets have misconfigured security policies or infected devices access **Amazon FSx for Windows File Server** shares.

The damage from **ransomware** goes beyond immediate operational and data losses; it severely affects reputation long-term. A company's failure to protect customer data may erode trust, causing customer attrition and affecting new business acquisition.

## **Moving beyond Cloud Storage to Cyberstorage**

**Malware** events continue to be a constant threat—**ransomware**, **zero-day exploits**, and unintended access threats are lurking at every corner. Despite having traditional backup methodologies and tools in place, organizations still fall victim. This is where the concept of **Cyberstorage** comes into play.

**Gartner** created a new category called **Cyberstorage** to categorize products that actively defend storage and data against cyber events through prevention, early detection and event blocking. **Superna** has been recognized as a leader in this category, appearing in the **Gartner** unstructured data storage and endpoint protection hypercycle reports.

Organizations rely on a variety of security tools from endpoint protection, **firewalls**, identity access management, and threat detection. They also implement data management strategies like **backups**, **snapshots**, and **immutability** features. But with **Cyberstorage**, security can be taken a step further.

When a cyber event occurs, **Superna's** solution can detect threats in real-time on **Amazon S3** and **FSx for Windows File Server**. Even stopping it immediately by cutting off access to at-risk users. Affected files are first isolated, then automatically recovered. Finally, a complete **audit trail** help provides the "**who, what and where**" for assisting in compliance and post-incident **forensic investigations**.

## **The Complex Security Landscape of Cyberstorage**

**Figure 1** shows how **Cyberstorage** framework defines several layers for an overall storage architecture.

*Figure 1: Superna Defender operates at the Data layer*

![Cyberstorage Framework](/images/3-BlogsTranslated/blog3/3.png)

Consider the typical enterprise security plan which includes components such as access controls, **encryption**, secure protocols, **antivirus software**, **firewalls**, and data loss prevention. These are often supplemented by **auditing**, **penetration testing**, backup and recovery mechanisms, and even physical security measures like security guards and locked doors.

While this security landscape is robust, it's also complex. A weakness at any point can have significant consequences. This leads us to a crucial question: it's often not a matter of "**if**" data will be affected by a cyber event, but "**when**". The effectiveness of an organization's response is vital.

**Superna Defender** protects your object and file storage at the **Data Layer**, providing an additional "**last line of defense**" where production data resides. By integrating **Cyberstorage** framework concepts, organizations can bolster their security posture to make sure they are better equipped to help prevent and respond to unintended access.

## **Criteria for the NIST Cyberstorage Checklist**

**Superna Defender** can also help customers comply with the points of the **National Institute of Standards and Technology (NIST) Cyberstorage Checklist**, as illustrated in **Figure 2**.

*Figure 2: NIST Cyberstorage Checklist, a part of the NIST Cybersecurity Framework*

![NIST Cyberstorage Checklist](/images/3-BlogsTranslated/blog3/4.png)

### **Identify**
To respond to suspicious activity, customers can use **NIST cybersecurity** models coupled with unique controls and rules for user and machine accounts.

### **Detect**
Using **machine learning**, this product monitors customer's offensive **Cyberstorage**, detects suspicious activity, and creates alerts and reports compatible with third-party software. It also provides simulated event capabilities to test incident response and security tool integrations.

### **Protect**
**Superna Defender** offers protection against **mass deletions**, **mass copies**, and provides **data loss prevention (DLP)** and custom activity pattern detections with **Active Auditor** for **AWS storage**. Events can be **forensically analyzed** to provide the "**who, what, and when**" root-case analysis of **Cyberstorage** events. Suspicious activity exceeding defined limits can trigger automatic user account lockouts for immediate security or alert storage administrators or security teams for manual review to prevent unnecessary business disruption from potentially **false positives**. **Learning mode** avoids **false positives** and autoconfigures itself based on observing activity.

### **Respond**
Central dashboards and alerts, powered by **webhooks**, a **Zero Trust API**, and integrations with **ServiceNow**, **Splunk**, **Palo Alto Networks**, and **AWS Security Hub**, provide seamless monitoring, reporting, and incident response. Automatically disabling user accounts, **API keys**, and **access tokens** can mitigate the effects of a **Cyberstorage** incident. Integrations with endpoint protection can extend responses to include host network isolation to further reduce the impact and spread.

### **Recover**
**Cyber Recovery Manager** provides recovery through analytics of a cyber event to determine when an event has happened, and tracking which files were impacted during the cyber event. This information allows for precise cyber recovery, restoring only affected files while leaving others unharmed, which shortens recovery times and increases productivity. The advanced monitoring system tracks real-time and historical user activity to speed up and improve incident investigation accuracy. Users can immediately see relevant information about the incident to understand what happened and which users were involved. Users can also review affected files and prioritize which are restored first.

## **Architecture Overview of Superna Defender in AWS**

**Superna Defender** is a **native AWS Marketplace deployment** and leverages several **AWS services** as shown in **Figure 3**. These services run a real-time event processing engine in a **pay-as-you-go** based consumption model that can be stopped and restarted on demand. This solution uses **Amazon EC2 Auto Scaling**, **VPCs**, and **security rules** to monitor and protect **Amazon S3** and **Amazon FSx for Windows File Server** storage.

*Figure 3: Superna Defender architecture diagram*

![Superna Defender Architecture](/images/3-BlogsTranslated/blog3/5.png)

## **Conclusion**

**Superna Defender**, integrating **AWS** and the **NIST Cyberstorage Framework**, provides a holistic cloud file and object storage security solution for customers. **Superna Defender** used with **Amazon S3** or **Amazon FSx for Windows File Server** can provide real-time **auditing** and monitoring of object and file storage in **AWS**. This allows customers to see the "**who, what, and where**" of file system events, allowing surgical point-in-time recovery of affected data.

Get started with **Superna Defender** on the **AWS Marketplace**, watch the **video demonstration** of **Superna Defender**, and read the **Gartner Innovation Insight Report** on how **Cyberstorage** mitigates the impact of **Cyberattacks**.

Customers should weigh the services they choose as their responsibilities vary depending on the services used, integrating those services into their **IT environment**, and applicable laws and regulations.
![Superna Defender Architecture](/images/3-BlogsTranslated/blog3/6.png)
## **Connect with Superna**

### **Superna – AWS Partner Spotlight**
**Superna** provides universal file and object **auditing** and threat mitigation for your **hybrid cloud** environments with a converged orchestration and security platform.

**Contact Superna** | **Partner Overview** | **AWS Marketplace**

**TAGS:** **Amazon FSx**, **AWS Partner Solution**, **Cloud Storage Security**, **Storage**, **Superna**