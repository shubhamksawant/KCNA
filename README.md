# Kubernetes-and-Cloud-Native-Associate (KCNA) Exam Guide

## Exam Overview

- **Duration:** 1.5 hours  
- **Passing Score:** 75%  
- **Certification Validity:** 3 years  
- **Prerequisite:** None  
- **Cost:** $250 USD (Includes 1-year exam eligibility with a free retake within the year)  
- **Result:** Emailed 24 hours after exam completion  

> **Tip:** Linux Foundation offers several discounts throughout the year during events like **CyberMonday**, **Kubecon**, and others. Be sure to take advantage of these opportunities.

---

## Official KCNA Curriculum
The KCNA exam consists of **60 MCQ questions** covering the following key topics:

| Topic                                  | Weightage |
|----------------------------------------|-----------|
| Kubernetes Fundamentals                | 46%       |
| Container Orchestration                | 22%       |
| Cloud Native Architecture              | 16%       |
| Cloud Native Observability             | 8%        |
| Cloud Native Application Delivery      | 8%        |

---

## Useful Keys & Common Acronyms in Kubernetes

- **K8s**: Kubernetes  
- **CNCF**: Cloud Native Computing Foundation  
- **NetPol**: Network Policies  
- **PV**: Persistent Volumes  
- **PVC**: Persistent Volume Claims  
- **CSI**: Container Storage Interface  
- **CNI**: Container Network Interface  
- **CI/CD**: Continuous Integration & Continuous Deployment  
- **RBAC**: Role Based Access Control  
- **OCI**: Open Container Initiative  
- **CRI**: Container Runtime Interface  
- **SMI**: Service Mesh Interface  
- **SLO**: Service Level Objectives  
- **SLI**: Service Level Indicators  
- **SLA**: Service Level Agreements  

---

## Topic-Wise Detailed Breakdown

### 1. Kubernetes Fundamentals (46%)
#### 1.1 Fundamental Kubernetes Resources
- **Pods**  
- **Deployments**  
- **Services**  
- **ReplicaSets**  
- **Headless Services**  

**Useful `kubectl` Commands:**
```bash
kubectl get pods                         # List pods in current namespace
kubectl get pods -A                      # List pods across all namespaces
kubectl api-resources                    # List retrievable API resources
kubectl run nginx --image=nginx          # Run an NGINX pod
kubectl create deploy kcna --image=nginx # Create a deployment
kubectl create deploy kcna --replicas=5  # Create deployment with 5 replicas
```

#### 1.2 Kubernetes Architecture
- Nodes
- Control Plane-Node Communication
- Kubernetes API Server

#### 1.4 Containers
- **What are Containers?**  
- **Containers vs VMs**  
- **Dockerfiles Best Practices**  

**References:**
- Kubernetes for Beginners
- Docker Tutorial for Beginners (Optional)
- Container Images Best Practices

#### 1.5 Scheduling
- The Kubernetes Scheduler
- Scheduling Framework & Pod Assignment

---

### 2. Container Orchestration (22%)
#### 2.1 Container Orchestration Fundamentals
- What is Kubernetes?
- Containers vs. Pods

#### 2.2 Runtime
- **Container Runtimes** (CRI, Docker deprecation)
- **Runtime Classes**

#### 2.3 Security
- The **4C's of Cloud Native Security**
- **RBAC (Role-Based Access Control)**
- Kubernetes Security Best Practices

#### 2.4 Networking
- **Cluster Networking**
- **Network Policies**
- **Services & Load Balancing**

#### 2.5 Service Mesh
- Introduction to **Service Mesh** (Istio, NGINX)

#### 2.6 Storage
- Persistent Volumes (PV) and Persistent Volume Claims (PVC)
- Kubernetes Storage Best Practices

---

### 3. Cloud Native Architecture (16%)
#### Topics Include:
- **Characteristics of Cloud Native Architecture**
- **Twelve-Factor App**
- **CNCF Landscape**
- **Monolithic vs Microservices Architecture**

#### 3.1 Autoscaling
- **Horizontal Pod Autoscaler (HPA)**
- Kubernetes Autoscaling Best Practices

#### 3.2 Serverless
- Serverless Architecture with Kubernetes
- **Knative**: Functions as a Service (FaaS)

#### 3.3 Community & Governance
- Kubernetes Community & Values
- Governance Best Practices

#### 3.4 Roles & Personas
- Kubernetes Roles & Use Cases

#### 3.5 Open Standards
- **OCI**, **CNI**, **CRI**, **CSI**  
- Service Mesh Standards

---

### 4. Cloud Native Observability (8%)
#### 4.1 Telemetry & Observability
- **OpenTelemetry** for Kubernetes
- Native Logging Mechanisms

#### 4.2 Prometheus
- Monitoring Kubernetes with **Prometheus**
- Prometheus Query Examples & Cheat Sheet

#### 4.3 Cost Management
- Cost Analysis & Optimization Strategies for Kubernetes

---

### 5. Cloud Native Application Delivery (8%)
#### 5.1 Application Delivery Fundamentals
- **CI/CD Pipelines** for Kubernetes
- **Infrastructure as Code (IaC)**

#### 5.2 GitOps
- **ArgoCD** vs **FluxCD**: Choosing the Right Tool
- Push vs Pull Pipelines

#### 5.3 CI/CD
- CI/CD Tools & Best Practices for Kubernetes

---

## References and Recommended Resources

1. [Kubernetes Official Documentation](https://kubernetes.io/docs/)
2. [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/)
3. [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/overview/)
4. [Prometheus Monitoring](https://prometheus.io/)
5. [GitOps with ArgoCD](https://argo-cd.readthedocs.io/en/stable/)

---

## Final Tips
1. Understand **key Kubernetes resources** such as Pods, Deployments, and Services.
2. Familiarize yourself with **kubectl commands**.
3. Master core concepts like **RBAC**, **Networking**, and **Observability**.
4. Practice Kubernetes scenarios using hands-on tools like Minikube or Rancher Desktop.
5. Take advantage of **CNCF community resources** and stay updated.

Good luck with your **KCNA Certification**!
