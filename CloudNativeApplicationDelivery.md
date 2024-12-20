
---

## **1. What is the main advantage of using Git as the single source of truth for both infrastructure and application resources?**  
**Answer:**  
- It provides **version control, transparency, and traceability** for all changes.

**Scenario:**  
When an application configuration issue occurs, Git history can be used to identify and rollback to a stable state.

---

## **2. What is a potential drawback of the pull-based deployment approach?**  
**Answer:**  
- Increased **latency** in deployment due to periodic polling of repositories by agents.

**Scenario:**  
In a high-velocity CI/CD environment, slight delays in synchronizing changes to production could impact time-sensitive deployments.

---

## **3. Which component of GitOps is responsible for monitoring the Kubernetes manifest repository and deploying resources to achieve the desired state?**  
**Answer:**  
- **GitOps Controller**, such as FluxCD or ArgoCD.

---

## **4. What happens when approved changes are pushed to Git in GitOps?**  
**Answer:**  
- The GitOps controller detects changes, pulls updates, and applies them to the cluster to match the desired state.

**Scenario:**  
A developer updates a deployment’s resource limits in a Git repository. The GitOps tool applies the updated configuration automatically.

---

## **5. What is FluxCD primarily focused on?**  
**Answer:**  
- Automating **pull-based deployments** and ensuring the cluster matches the desired state defined in Git.

---

## **6. How can a developer update the Kubernetes manifest repository after pushing a newly built image to the container registry?**  
**Answer:**  
- By updating the **image tag** in the deployment manifest file stored in Git.

**Scenario:**  
After building a new version of an application image, the developer updates the `image` field in the manifest to `app:v2.0`.

---

## **7. What is the key advantage of using GitOps for managing infrastructure changes?**  
**Answer:**  
- **Automated rollbacks and recovery** by reverting to previous states stored in Git.

**Scenario:**  
If a faulty configuration is deployed, reverting to the last known stable state is as simple as a Git rollback.

---

## **8. Main Difference Between Push-Based and Pull-Based Deployment Approaches**  
**Answer:**  
- **Push-Based:** Changes are pushed directly to the cluster.  
- **Pull-Based:** Agents within the cluster pull changes from the Git repository.

---

## **9. Command in GitOps with ArgoCD to Rollback**  
**Answer:**  
- `argocd app rollback <app-name> <revision>`

---

## **10. Main Benefit of Continuous Deployment (CD)**  
**Answer:**  
- Faster delivery of new features with **minimal manual intervention**.

---

## **11. Benefit of a Pull-Based Deployment Approach**  
**Answer:**  
- **Enhanced security** as cluster credentials are not exposed outside the cluster.

---

## **12. How a Pull-Based Approach Supports Multi-Tenant Kubernetes**  
**Answer:**  
- By segregating tenants into different namespaces and syncing repositories specific to each namespace.

---

## **13. Goal of GitOps Working Group Under CNCF**  
**Answer:**  
- To establish **standards and best practices** for GitOps implementations.

---

## **14. Purpose of Using a GitOps Tool to Reconcile System State**  
**Answer:**  
- Ensures the cluster always matches the desired state in Git by identifying and correcting drifts.

---

## **15. Purpose of GitOps**  
**Answer:**  
- Simplify and automate **infrastructure management** using Git as the single source of truth.

---

## **16. Governing Body for Kubernetes Project**  
**Answer:**  
- **Cloud Native Computing Foundation (CNCF)**.

---

## **17. GitOps Tool Covering the Entire CI/CD Process**  
**Answer:**  
- **ArgoCD**.

---

## **18. How GitOps Ensures Changes Are Deployed**  
**Answer:**  
- By using a **continuous reconciliation loop** to apply changes stored in Git to the cluster.

---

## **19. What Does ArgoCD Do When It Detects Changes in the Repository?**  
**Answer:**  
- Pulls the changes and synchronizes the cluster to the new state.

---

## **20. Main Challenge Before Implementing CI/CD**  
**Answer:**  
- Slow and error-prone **manual deployments**.

---

## **21. Purpose of OpenGitOps Project**  
**Answer:**  
- To define **open standards** and foster collaboration on GitOps practices.

---

## **22. How Desired State Is Versioned in GitOps**  
**Answer:**  
- By storing Kubernetes manifests or Helm charts in **version-controlled Git repositories**.

---

## **23. Tool Allowing Multiple Git Repositories for Deployments**  
**Answer:**  
- **ArgoCD**.

---

## **24. Issues with Manual Changes to Resources Using CLI**  
**Answer:**  
- Lack of **traceability and consistency**, leading to potential drift between the live and desired state.

---

## **25. Continuous Integration (CI) Benefits**  
**Answer:**  
- **Early bug detection** through automated tests.

---

## **26. How GitOps Simplifies Disaster Recovery**  
**Answer:**  
- Re-applying manifests from Git ensures **quick restoration** of the desired state.

---

## **27. Updates in Pull-Based Deployment**  
**Answer:**  
- Initiated by **cluster agents**, which continuously sync changes from the Git repository.

---

## **28. GitOps Principle: Describing Entire System Declaratively**  
**Answer:**  
- Ensures the system state is **codified and stored** in Git.

---

## **29. Approach Exposing Cluster Credentials**  
**Answer:**  
- **Push-Based Deployment**.

---

## **30. Main Benefit of Using GitOps for Kubernetes**  
**Answer:**  
- Automates **infrastructure and application management** while maintaining auditability.

---

## **31. Commonly Used GitOps Tool for Automation**  
**Answer:**  
- **FluxCD** or **ArgoCD**.

---

## **32. GitOps Tool Developed by Weaveworks**  
**Answer:**  
- **FluxCD**, now a CNCF graduated project.

---
