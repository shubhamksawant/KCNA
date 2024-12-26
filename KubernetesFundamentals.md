
---

## **1. Where can you find containerized versions of applications readily available for use?**  
**Answer:**  
- Containerized versions of applications are available on **container registries** like:  
  - Docker Hub  
  - Google Container Registry (GCR)  
  - Amazon Elastic Container Registry (ECR)

**Scenario:**  
To pull an image from Docker Hub:  
```bash
docker pull nginx
```

---

## **2. Primary Purpose of Docker (vs. Hypervisors)**  
**Answer:**  
- Docker creates lightweight containers that share the host OS kernel, whereas hypervisors virtualize entire operating systems.  
- Docker is faster and uses fewer resources compared to hypervisors.

---

## **3. Container Orchestration Technology Known for Customization**  
**Answer:**  
- **Kubernetes** is powerful but complex to set up. It allows for customization in deployments, scaling, and resource management.

---

## **4. Benefit of Using Container Runtimes Supporting the CRI**  
**Answer:**  
- Ensures compatibility with Kubernetes' **Container Runtime Interface**.  
- Facilitates swapping runtimes without changing Kubernetes configurations.

---

## **5. Kubernetes Component Responsible for Decisions on Failures**  
**Answer:**  
- **Kube Controller Manager** handles failures by creating new pods or endpoints.

---

## **6. Container Runtime Used with Kubernetes**  
**Answer:**  
- Kubernetes supports **ContainerD**, **CRI-O**, and others compliant with CRI.

---

## **7. What is Containerization?**  
**Answer:**  
- A method of packaging applications with their dependencies in isolated environments called containers.

---

## **8. Kubernetes Component for Cluster Interaction**  
**Answer:**  
- **Kubectl** is the command-line tool for managing Kubernetes clusters.

---

## **9. How Containers Differ from VMs (OS Kernel)**  
**Answer:**  
- Containers share the host OS kernel. VMs require their own kernel.

---

## **10. Kubernetes Component Distributing Containers Across Nodes**  
**Answer:**  
- **Kube Scheduler** assigns pods to nodes.

---

## **11. Command to Run a Container with NerdCTL**  
**Answer:**  
```bash
nerdctl run --name red alpine
```

---

## **12. Role of the Master Node in Kubernetes**  
**Answer:**  
- Controls the cluster and manages:  
  - Scheduling  
  - API requests  
  - Monitoring and scaling  

---

## **13. Components Installed When Setting up Kubernetes**  
**Answer:**  
- **Master Node Components:** API server, Scheduler, Controller Manager, etcd.  
- **Worker Node Components:** Kubelet, Kube Proxy, Container runtime.

---

## **14. NerdCTL Option for Port Mapping**  
**Answer:**  
Use `-p` to map ports.  
```bash
nerdctl run -p 8080:80 nginx
```

---

## **15. Why Was Dockershim Removed in Kubernetes 1.24?**  
**Answer:**  
- To move to CRI-compliant runtimes like ContainerD and CRI-O for better integration and performance.

---

## **16. What is DevOps?**  
**Answer:**  
- A cultural practice combining **Development** and **Operations** to deliver applications faster.

---

## **17. Containers on Ubuntu OS**  
**Answer:**  
- You can run containers based on any OS supported by Docker images (e.g., Alpine, Debian).

---

## **18. Primary Function of Kubernetes Node (Minion)**  
**Answer:**  
- Nodes run application workloads by hosting pods.

---

## **19. Who Maintains CRI Control?**  
**Answer:**  
- **Cloud Native Computing Foundation (CNCF)** develops and maintains CRI-O and related tools.

---

## **20. Role of Kubelet**  
**Answer:**  
- Ensures containers are running as specified by the pod definitions.

---

## **21. Command to Pull a Redis Image Using CTR**  
**Answer:**  
```bash
ctr images pull docker.io/library/redis:latest
```

---

## **22. Container Orchestration Not Mentioned**  
**Answer:**  
- **Mesos** is an orchestration tool but wasn’t mentioned.

---

## **23. Why Docker Images Work Seamlessly in Kubernetes**  
**Answer:**  
- Kubernetes supports Docker images via ContainerD or CRI-O runtimes.

---

## **24. Purpose of `kubectl` Tool in Kubernetes**  
**Answer:**  
- Manages clusters and resources (e.g., pods, deployments, nodes).

---

## **25. Command to Run MongoDB Instance Using Docker**  
**Answer:**  
```bash
docker run --name mongodb -d mongo
```

---

## **26. Relationship Between Container Image and Container**  
**Answer:**  
- A **container** is a running instance of a **container image**.

---

## **27. Command to Run a Container Using CTR**  
**Answer:**  
```bash
ctr run docker.io/library/nginx:latest my-nginx
```

---

## **28. Common Kubectl Command for Deployment**  
**Answer:**  
```bash
kubectl apply -f deployment.yaml
```

---

## **29. Command to View Cluster Information**  
**Answer:**  
```bash
kubectl cluster-info
```

---

## **30. Kubernetes Master Node Components**  
**Answer:**  
- API server, Controller Manager, Scheduler, etcd.

---

## **31. What is a Kubernetes Cluster?**  
**Answer:**  
- A group of nodes working together to manage and run containerized applications.

---

## **32. Role of etcd in Kubernetes**  
**Answer:**  
- Stores the cluster's configuration and state.

---

## **33. Automated Process of Managing Containers**  
**Answer:**  
- Known as **Container Orchestration**.

---

## **34. Features in NerdCTL Not in Docker**  
**Answer:**  
- Native support for container snapshots and alternative container runtimes.

---

## **35. Primary Role of Kubernetes**  
**Answer:**  
- Manages containers by automating deployment, scaling, and networking.

---

## **36. What is CRI?**  
**Answer:**  
- **Container Runtime Interface** ensures Kubernetes can interact with any compliant runtime.

---

## **37. Purpose of Dockershim**  
**Answer:**  
- Acts as a bridge between Docker and Kubernetes before CRI support.

---

## **38. What is Cloud Native?**  
**Answer:**  
- Developing applications designed to run in distributed cloud environments.

---

## **39. Essential Element of Cloud Native**  
**Answer:**  
- **Containers** are fundamental for portability and scalability.

---

## **40. Container Technology Docker Uses**  
**Answer:**  
- **Linux Containers (LXC)** and **ContainerD**.

---

## **41. What are Containers?**  
**Answer:**  
- Containers are lightweight, isolated environments to run applications with their dependencies.

