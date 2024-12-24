
---

# **Kubernetes Networking Q&A Guide**

This document provides answers, practical examples, and scenarios for Kubernetes networking-related questions.

---

## **1. Which layer of networking is crucial for the functioning of a cluster at the pod level?**  
**Answer:**  
- The **Network Layer (Layer 3)** is crucial for pod-to-pod communication and service discovery.

---

## **2. Does Kubernetes deploy a built-in DNS server by default?**  
**Answer:**  
- Yes, Kubernetes deploys a built-in DNS server called **CoreDNS** by default.

**Scenario:**  
When a service is created, CoreDNS automatically creates a DNS entry for it.

---

## **3. What does the "type" field indicate when set to "host-local" under the IPAM section in a CNI plugin configuration file?**  
**Answer:**  
- It specifies that IP addresses will be allocated from a local host pool.

---

## **4. Kubelets on Master and Worker Nodes**  
**Answer:**  
- **True**. Kubelets can run on both master and worker nodes to manage pod lifecycles.

---

## **5. Network Connectivity Requirements for Kubernetes Nodes**  
**Answer:**  
- All nodes must have **full network connectivity** to communicate with each other and with pods.

---

## **6. Does Kubernetes Provide a Built-in Solution for Pod Networking?**  
**Answer:**  
- No, Kubernetes relies on **Container Network Interface (CNI)** plugins like Calico, Flannel, or Weave.

---

## **7. Where is the CNI Plugin Configured?**  
**Answer:**  
- The plugin configuration is stored in `/etc/cni/net.d/`.

---

## **8. Fully Qualified Domain Name (FQDN) for a Service**  
**Answer:**  
- For a service `web-service` in namespace `apps`:  
  ```
  web-service.apps.svc.cluster.local
  ```

---

## **9. Popular Networking Solutions for Kubernetes**  
**Answer:**  
- **Calico**, **Flannel**, **Weave Net**, and **Cilium**.

---

## **10. Responsibility of a Container Runtime in Networking**  
**Answer:**  
- The runtime connects containers to the network using the configured CNI plugin.

---

## **11. How Pods and Services are Grouped in DNS Subdomain**  
**Answer:**  
- Pods and services in a namespace are grouped under:  
  ```
  <namespace>.svc.cluster.local
  ```

---

## **12. DNS Record for a Kubernetes Service**  
**Answer:**  
- Maps the service name to its **Cluster IP**.

---

## **13. What Happens When a Kubernetes Service is Created?**  
**Answer:**  
- A **ClusterIP** is assigned, and DNS entries are created by CoreDNS.

---

## **14. Purpose of the "ipMasquerade" Field in CNI Configuration**  
**Answer:**  
- Determines if outgoing traffic from pods should masquerade the pod’s IP.

---

## **15. Ports on Which Kubelets Listen**  
**Answer:**  
- Kubelets listen on **10250** for HTTPS and **10255** for HTTP.

---

## **16. "isGateway" Field in CNI Configuration**  
**Answer:**  
- Specifies if the host should act as a **gateway** for the container network.

---

## **17. Ports Required by kube-controller-manager**  
**Answer:**  
- Listens on **10257** for HTTPS.

---

## **18. Ports Used by Worker Nodes for External Services**  
**Answer:**  
- Typically, **30000-32767** (NodePort range).

---

## **19. Naming Convention for Pod Records in DNS**  
**Answer:**  
- Records use the format:  
  ```
  <pod-ip>.<namespace>.pod.cluster.local
  ```

---

## **20. Requirements for Pod Networking in Kubernetes**  
**Answer:**  
1. Pods must communicate across nodes without NAT.  
2. All nodes must have a unique, routable IP.  

---

## **21. Ports Required for ETCD Client Communication**  
**Answer:**  
- ETCD clients communicate on **2379** and peers on **2380**.

---

## **22. Where Are Services Grouped in DNS Subdomain?**  
**Answer:**  
- Under the subdomain:  
  ```
  svc.cluster.local
  ```

---

## **23. Referencing a Service in Another Namespace**  
**Answer:**  
- Use the full service name:  
  ```
  <service-name>.<namespace>.svc.cluster.local
  ```

---

## **24. How Pods Reach Services Using Names**  
**Answer:**  
- CoreDNS resolves the service name to its ClusterIP.

---

## **25. Unique Identifiers Required for Hosts in Networking**  
**Answer:**  
- **IP Address** and **Hostname**.

---

## **26. IPAM Section in CNI Plugin Configuration**  
**Answer:**  
- Defines the **IP allocation method**, such as "host-local" or "dhcp".

---

## **27. Port for Kubernetes API Server**  
**Answer:**  
- Typically **6443**.

---

## **28. CNI Plugin Lookup by Kubelet**  
**Answer:**  
- The kubelet checks the directory `/etc/cni/net.d/`.

---

## **29. Command to View Running Kubelet Service**  
**Answer:**  
```bash
systemctl status kubelet
```

---

## **30. How Pods Access Services in Kubernetes**  
**Answer:**  
- Pods access services by their **ClusterIP** or service name.

---

## **31. Port Required by kube-scheduler**  
**Answer:**  
- Listens on **10259** for HTTPS.

---

## **32. Requirement for Every Interface on a Node**  
**Answer:**  
- Must have a **unique IP address** and proper routing rules configured.

---
