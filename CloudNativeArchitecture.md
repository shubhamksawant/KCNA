
---

## **1. What is the role of Working Groups in the Kubernetes community?**  
**Answer:**  
- Working Groups (WGs) focus on **cross-cutting concerns** that involve collaboration between multiple SIGs or require specialized focus.  

**Scenario:**  
A WG might address integration challenges between Kubernetes and external tools like Helm, requiring expertise from different SIGs.

---

## **2. What is the recommended way to propose a change in Kubernetes?**  
**Answer:**  
- Submit a **Kubernetes Enhancement Proposal (KEP)** via the GitHub repository.  

**Scenario:**  
Proposing a new autoscaling algorithm would require a detailed KEP outlining its motivation, design, and implementation.

---

## **3. How does FaaS handle scaling?**  
**Answer:**  
- FaaS dynamically **scales functions up or down** based on incoming requests, using the **pay-as-you-go model**.

**Scenario:**  
An e-commerce app using AWS Lambda scales during flash sales, handling traffic spikes efficiently without manual intervention.

---

## **4. Which of the following is not a Kubernetes Special Interest Group (SIG)?**  
**Answer:**  
- Example: **SIG Virtualization** (if hypothetical).

---

## **5. Which standard created by the OCI outlines how a file system bundle should be packaged into an image?**  
**Answer:**  
- **OCI Image Specification**.

---

## **6. Which section of a KEP outlines the motivation and goals of a proposed change or feature?**  
**Answer:**  
- The **Motivation** section.

---

## **7. Limitations of Using GitHub Issues for Proposing Changes in Kubernetes**  
**Answer:**  
- Lack of structured discussion and tracking for complex features or enhancements.

---

## **8. What is the purpose of Cluster Autoscaler in Kubernetes?**  
**Answer:**  
- Adjusts the number of nodes in a cluster based on resource demands.

**Scenario:**  
A cluster running low on CPU automatically adds nodes to handle an increased workload.

---

## **9. Role of Kubernetes Steering Committee**  
**Answer:**  
- Governs the overall project, including processes, funding, and community management.

---

## **10. Problem with Using Different Container Technologies Without Open Standards**  
**Answer:**  
- Leads to **vendor lock-in** and interoperability challenges.

---

## **11. Who Developed the Kubernetes Project?**  
**Answer:**  
- **Google**, later donated to the CNCF.

---

## **12. Benefits of Using FaaS**  
**Answer:**  
- **Cost efficiency** and automatic scaling.

**Scenario:**  
A news aggregator runs only during breaking news events, reducing idle server costs.

---

## **13. How Are SIG Leaders Elected in Kubernetes?**  
**Answer:**  
- By the community through **voting or consensus**.

---

## **14. When Did Kubernetes Join CNCF?**  
**Answer:**  
- **2016**.

---

## **15. Autoscaling in Computing**  
**Answer:**  
- Automatically adjusting resources to meet current demands.

---

## **16. Purpose of Kubernetes SIG Network**  
**Answer:**  
- Focuses on networking-related features like **Service, Ingress, and NetworkPolicy**.

---

## **17. Pod-Based Scaling in Kubernetes Autoscaling**  
**Answer:**  
- Horizontal scaling of **pods** using the **Horizontal Pod Autoscaler (HPA)**.

---

## **18. How KEPs Address GitHub Issue Limitations**  
**Answer:**  
- By providing a **structured template** for complex proposals.

---

## **19. How Individuals Can Contribute to Kubernetes**  
**Answer:**  
- Join SIGs, attend meetings, and submit KEPs or code contributions.

---

## **20. Pay-As-You-Go Model in FaaS**  
**Answer:**  
- Users are billed only for the **actual execution time** of functions.

---

## **21. Drawbacks of Traditional Server Management**  
**Answer:**  
- High costs, underutilization, and lack of scalability.

---

## **22. Purpose of Autoscaling**  
**Answer:**  
- Ensures optimal resource usage and performance during demand fluctuations.

---

## **23. Purpose of Vertical Pod Autoscaler in Kubernetes**  
**Answer:**  
- Adjusts **CPU and memory** requests/limits for individual pods.

---

## **24. Cloud Providers Offering FaaS**  
**Answer:**  
- AWS Lambda, Azure Functions, Google Cloud Functions, etc.

---

## **25. Container Runtime Interface (CRI)**  
**Answer:**  
- Provides flexibility by allowing Kubernetes to use different container runtimes like **containerd** and **CRI-O**.

---

## **26. What is Function-as-a-Service (FaaS)?**  
**Answer:**  
- A serverless computing model where **functions** are executed in response to events.

---

## **27. Kubernetes Autoscaling Feature That Adjusts the Cluster**  
**Answer:**  
- **Cluster Autoscaler**.

---

## **28. Kubernetes Autoscaling Feature That Adjusts Pod Counts**  
**Answer:**  
- **Horizontal Pod Autoscaler (HPA)**.

---

## **29. Provisional Status in KEP Workflow**  
**Answer:**  
- Indicates the proposal is under **initial review** but not yet approved.

---

## **30. What is Serverless Computing?**  
**Answer:**  
- A cloud-native model where developers manage **functions, not servers**.

---

## **31. Kubernetes Enhancement Proposal (KEP)**  
**Answer:**  
- A structured document to propose significant changes or features in Kubernetes.

---

## **32. Purpose of a Test Plan in a KEP**  
**Answer:**  
- Ensures that the proposed feature works as expected.

---

## **33. Horizontal vs. Vertical Scaling**  
**Answer:**  
- Horizontal: Adds more instances.  
- Vertical: Increases resources of existing instances.

---

## **34. Kubernetes Steering Committee**  
**Answer:**  
- Governs the project and defines community standards.

---

## **35. Open Container Initiative (OCI)**  
**Answer:**  
- Created standards for **container images and runtimes**.

---

## **36. Benefit of Kubernetes Autoscaling**  
**Answer:**  
- Optimizes resource usage while maintaining application performance.

---

## **37. Open Standards in Cloud Native Ecosystem**  
**Answer:**  
- Promote **interoperability and flexibility**.

---

## **38. Autoscaling Resource Allocation for Individual Pods**  
**Answer:**  
- **Vertical Pod Autoscaler** adjusts resource limits and requests dynamically.

---

## **1. Three Key Factors Essential for Achieving True Cloud-Native Autoscaling**
**Answer:**
1. **Dynamic resource allocation** based on workload demands.
2. **Declarative configuration** for desired system states.
3. **Observability and monitoring** to trigger scaling decisions.

**Scenario:**
A video streaming platform automatically scales its backend services during live events to handle sudden traffic surges.

---

## **2. Most Common Form of Serverless Computing**
**Answer:**
- **Function-as-a-Service (FaaS)**

**Scenario:**
An e-commerce website uses AWS Lambda to execute payment processing functions only when a customer makes a purchase.

---

## **3. Two-Layered Approach Kubernetes Utilizes for Autoscaling**
**Answer:**
1. **Pod Autoscaling** using the Horizontal Pod Autoscaler (HPA).
2. **Cluster Autoscaling** to adjust the number of nodes.

**Scenario:**
A Kubernetes cluster increases the number of pods during peak traffic and scales the cluster nodes as needed to support the pods.

---

## **4. Kubernetes Autoscaling Feature for Cluster Resizing**
**Answer:**
- **Cluster Autoscaler**

**Scenario:**
A data analytics platform expands its cluster during intensive computation tasks and shrinks it during off-peak hours.

---

## **5. Kubernetes Autoscaling Feature for Adjusting Pod Counts**
**Answer:**
- **Horizontal Pod Autoscaler (HPA)**

**Scenario:**
An API service increases the number of pods to handle increased API requests and scales down during low demand.

---

## **6. Significance of Provisional Status in KEP Workflow**
**Answer:**
- Indicates that the proposal is under **initial review** and needs further discussion and approval.

**Scenario:**
A proposal for a new Kubernetes scheduling algorithm receives provisional status as it awaits input from SIG-Scheduling.

---

## **7. How Proposed Changes or New Features Are Documented in Kubernetes**
**Answer:**
- Through **Kubernetes Enhancement Proposals (KEPs)**.

**Scenario:**
A developer documents the addition of a new autoscaling feature using a structured KEP.

---

## **8. What is Serverless Computing?**
**Answer:**
- A cloud-native model where developers focus on functions without managing underlying servers.

**Scenario:**
A photo-sharing app processes image uploads using serverless functions that run only when triggered by user actions.

---

## **9. Purpose of a Kubernetes Enhancement Proposal (KEP)**
**Answer:**
- To propose and track significant changes or features in Kubernetes.

**Scenario:**
A KEP is created to introduce a new feature for scaling stateful applications.

---

## **10. Purpose of a Test Plan in a KEP**
**Answer:**
- Ensures that the proposed feature functions correctly and meets the intended goals.

**Scenario:**
A test plan in a KEP validates a new network policy feature under various scenarios.

---

## **11. Benefit of Horizontal Scaling Over Vertical Scaling**
**Answer:**
- Horizontal scaling provides **better fault tolerance** and scalability by distributing the load across multiple instances.

**Scenario:**
A web application adds more servers during high traffic to maintain performance instead of upgrading a single server.

---

## **12. Role of the Kubernetes Steering Committee**
**Answer:**
- Oversees project governance, ensures adherence to community standards, and manages funding.

**Scenario:**
The Steering Committee resolves disputes between SIGs over feature priorities.

---

## **13. Open Container Initiative (OCI) and Its Standards**
**Answer:**
- OCI defines standards for container images and runtimes to promote interoperability.

**Scenario:**
Different cloud platforms can run the same container image due to OCI compliance.

---

## **14. Section of a KEP That Outlines Motivation and Goals**
**Answer:**
- The **Motivation** section.

**Scenario:**
A KEP’s Motivation section explains why a new storage feature is needed for high-performance applications.

---

## **15. Cloud Service Provider Offering AWS Lambda**
**Answer:**
- **Amazon Web Services (AWS)**

**Scenario:**
AWS Lambda is used for processing log data from an application in real-time.

---

## **16. Purpose of Cluster Autoscaler in Kubernetes Autoscaling**
**Answer:**
- Adjusts the number of nodes in a cluster based on resource utilization.

**Scenario:**
A big data cluster automatically adds nodes to process a large dataset during peak operations.

---

## **17. Purpose of Horizontal Pod Autoscaler in Kubernetes Autoscaling**
**Answer:**
- Adjusts the number of pods based on metrics like CPU or memory usage.

**Scenario:**
An online gaming platform scales up pods during tournaments to handle player traffic.

---

## **18. What Are SIGs in the Kubernetes Community?**
**Answer:**
- Special Interest Groups (SIGs) manage specific areas of Kubernetes development.

**Scenario:**
SIG-Network focuses on features like Ingress and DNS within Kubernetes.

---

## **19. Benefit of Kubernetes Autoscaling**
**Answer:**
- Optimizes resource usage while ensuring application performance during demand fluctuations.

**Scenario:**
A news website scales dynamically to handle spikes in traffic during breaking news events.

---

## **20. Why Kubernetes Is Powerful for Cloud-Native Autoscaling**
**Answer:**
- It supports declarative configuration, real-time monitoring, and seamless scaling across pods and clusters.

**Scenario:**
A machine learning platform leverages Kubernetes autoscaling to manage varying workloads effectively.

---

## **21. Purpose of Open Standards in Cloud-Native Ecosystem**
**Answer:**
- Promote interoperability, flexibility, and vendor neutrality.

**Scenario:**
Developers use OCI-compliant containers across different cloud providers without modification.

---

## **22. Kubernetes Autoscaling Feature for Adjusting Pod Resources**
**Answer:**
- **Vertical Pod Autoscaler (VPA)**

**Scenario:**
A database adjusts its CPU and memory allocation dynamically during peak query loads.

---
