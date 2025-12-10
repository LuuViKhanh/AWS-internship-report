---
title: "Event 4"
weight: 1
chapter: false
pre: " <b> 4.4. </b> "
---

## Event Report: Specialized Workshop on Edge Network Services

### Event Purpose
- The workshop was organized to provide participants with a comprehensive view of how to optimize and protect web systems through AWS edge services. Main objectives:
   - Learn more about challenges when operating Internet applications at scale.
   - Learn how Amazon CloudFront addresses performance, cost, and security issues.
   - Explore CloudFront's core features and operational mechanisms.
   - Discover security services such as AWS WAF, AWS Shield, and Bot Control.
   - Hands-on practice optimizing web apps and protecting Internet applications.

---

### Speaker List & Topics

#### FROM EDGE TO ORIGIN: CloudFront as Your Foundation
- **Nguyen Gia Hung** – Head of Solutions Architect, Amazon Web Services Vietnam

#### Defense from Public Threats: AWS WAF & Application Protection
- **Julian Lu** – Sr. Edge Specialist Solutions Architect at Amazon Web Services (AWS)

---

### Highlighted Content

#### 1. Challenges in Operating Internet Applications
The workshop opened by analyzing common issues businesses typically face:
- High latency due to users being far from the origin server.
- Heavy load on backend systems leading to increased costs.
- Internet attacks such as DDoS, bot traffic, injection, and scraping.
- Difficulty scaling when traffic suddenly spikes.
- Lack of edge defense layer, making the origin vulnerable to direct attacks.

#### 2. CloudFront – The Foundation Solution "From Edge to Origin"
- Speakers presented how CloudFront helps improve systems:
  - Caching to reduce load on origin.
  - Global Edge Network allows users to access from the nearest location → increased performance.
  - Security at Edge with WAF, Shield, and Bot Control at the edge.
  - Cost Optimization by reducing direct requests to origin.
  - Resiliency & Availability through global distribution and failover mechanisms.

#### 3. How CloudFront Works
- A simple architecture model was presented:
  1. User sends request → goes to the nearest Edge Location.
  2. CloudFront checks for cached content.
  3. If not available → request is forwarded to origin.
  4. Edge caches content to serve subsequent requests.
  => This process helps increase speed while reducing costs and enhancing protection.

#### 4. Protecting Applications from Threats
- **AWS WAF – Web Application Firewall**:
  - Filters and blocks common attack types: SQL injection, XSS, unauthorized access, etc.
  - Can configure rules, rule groups, and managed rules.
  - Operates directly on CloudFront → protects at the edge layer, reducing burden on origin.

- **AWS WAF Bot Control**:
  - Identifies bots, distinguishes good bots from bad bots.
  - Blocks scraping, brute force, and bad automated traffic.
  - Reduces load and increases system security.

- **AWS Shield**:
  - Provides DDoS protection at multiple levels.
  - Shield Standard (free) is always enabled for CloudFront.
  - Shield Advanced supports monitoring, incident response, and optimized protection costs.

---

### Personal Experience and Lessons Learned

- **Learning from AWS experts**:
  - Speakers shared difficulties and challenges in deploying large-scale systems and managing traffic.
  - Knowledge about caching, edge layer security, and performance optimization was explained very clearly.

- **Technical experience**:
  - Analyzed real architecture diagrams and simulated CloudFront's request processing flow.
  - Explored how to build WAF rules and Bot Control mechanisms.
  - Clearly understood how CloudFront combines with Shield to prevent DDoS.

- **Hands-on Workshop**:
  - **Optimize Internet Web Application**:
      - Configured CloudFront, set up caching policies, and verified latency improvements.
  - **Secure Internet Web Application**:
      - Created and applied WAF rules.
      - Observed bot traffic and created blocking rules.
      - Integrated CloudFront + WAF + Shield.

---

### Results Achieved

- Learned more about the critical role of the edge layer in modern Internet application architecture — not only for accelerating content delivery but also for creating an effective defense layer.
- Able to explain and deploy architecture models where CloudFront serves as the entry point for all web applications, helping optimize performance and increase security levels.
- Learned more about how AWS Shield works and can effectively apply it to protect applications from DDoS attacks without complex configuration.
- Grasped the coordination mechanism between CloudFront – WAF – Shield to create a comprehensive, resilient, and cost-effective defense layer.

---

### Event Photos
![Edge Network Services Event](/images/4-EventParticipated/event4_1.png)
![Edge Network Services Event](/images/4-EventParticipated/event4_2.png)
