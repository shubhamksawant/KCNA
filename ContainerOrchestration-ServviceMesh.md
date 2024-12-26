---

## **1. How do proxies communicate with each other in a service mesh architecture?**  
**Answer:**  
- Proxies communicate through **mutual TLS (mTLS)** connections to ensure secure communication.

**Scenario:**  
In an Istio service mesh, each pod has an Envoy proxy sidecar. These proxies encrypt data and authenticate communication between services.

---

## **2. Which feature of a service mesh enables automatic detection and registration of services within a network?**  
**Answer:**  
- **Service Discovery** allows automatic detection and registration of services.

**Scenario:**  
When a new service is deployed in Kubernetes, the service mesh automatically detects it and updates routing rules.

---

## **3. Significant Achievement of Envoy in CNCF**  
**Answer:**  
- Envoy graduated as a **CNCF project**, showcasing its stability and widespread adoption.

---

## **4. Which type of service must be created in Kubernetes to make an application accessible outside the cluster?**  
**Answer:**  
- A **LoadBalancer** service.

**Scenario:**  
If you want users to access a web app running on Kubernetes, you would expose it using a LoadBalancer service.

---

## **5. How does Kubernetes services identify and select specific pods from a large pool of other pods?**  
**Answer:**  
- By using **labels** and **selectors**.

**Scenario:**  
A service with the label `app: web` selects only pods tagged with `app: web`.

---

## **6. Which of the following is NOT one of the three types of services in Kubernetes?**  
**Answer:**  
- **Proxy** is NOT a service type. Kubernetes has **ClusterIP**, **NodePort**, and **LoadBalancer** services.

---

## **7. Which of the following is NOT a main topic covered by service discovery in a service mesh?**  
**Answer:**  
- **Database Schema Discovery** is not related to service mesh.

---

## **8. Components Originally Part of Istio Control Plane**  
**Answer:**  
- **Citadel**, **Pilot**, and **Galley**.

---

## **9. Tasks Performed by Sidecar Containers in Kubernetes**  
**Answer:**  
- Traffic management, logging, and service communication.

**Scenario:**  
A sidecar container like Envoy intercepts all incoming and outgoing traffic in an Istio service mesh.

---

## **10. Default Type of Service in Kubernetes**  
**Answer:**  
- **ClusterIP**, which facilitates communication between services within the cluster.

---

## **11. What is Istio Known for in Complex Deployments?**  
**Answer:**  
- Managing **traffic routing**, security, and observability.

**Scenario:**  
In a microservice architecture, Istio enables version-based routing to roll out updates gradually.

---

## **12. Term for Creating and Killing Pods in Kubernetes**  
**Answer:**  
- **Ephemeral**. Pods are ephemeral and can be created or destroyed based on demand.

---

## **13. Technology Used by Istio to Implement Proxies**  
**Answer:**  
- **Envoy**.

---

## **14. True Statement About Proxy Service in Application Architecture**  
**Answer:**  
- Proxies handle tasks like **routing, load balancing, and security**.

---

## **15. Term for Additional Containers Supporting Main Containers**  
**Answer:**  
- **Sidecar Containers**.

**Scenario:**  
A sidecar container might handle logging for the main application container.

---

## **16. Primary Purpose of Load Balancing in a Service Mesh**  
**Answer:**  
- To **distribute traffic** evenly across multiple instances of a service.

---

## **17. Feature of a Service Mesh That Provides Secure Communication**  
**Answer:**  
- **Mutual TLS (mTLS)**.

---

## **18. How Applications Communicate in Kubernetes**  
**Answer:**  
- Using **ClusterIP** or DNS names provided by Kubernetes services.

**Scenario:**  
A frontend service can communicate with a backend service by its DNS name, such as `backend.default.svc.cluster.local`.

---

## **19. Primary Function of Envoy**  
**Answer:**  
- Acts as a **proxy** for service communication, providing observability and traffic management.

---

## **20. Role of the Control Plane in a Service Mesh Architecture**  
**Answer:**  
- Manages **configuration** and policies for the data plane.

---

## **21. True Statement About Istio**  
**Answer:**  
- Istio provides **traffic management, security, and observability** for microservices.

---

## **22. Component in Istio Delivering Configuration Secrets to Envoy Proxies**  
**Answer:**  
- **Citadel**.

---

## **23. Role of a Service Mesh in Microservice Architecture**  
**Answer:**  
- Simplifies **service-to-service communication** by managing routing, security, and monitoring.

---

## **24. Istio Component Combining Citadel, Pilot, and Galley**  
**Answer:**  
- **Istiod**.

---

## **25. Key Difference Between LoadBalancer and NodePort Services in Kubernetes**  
**Answer:**  
- **LoadBalancer** services provide external IPs, while **NodePort** exposes services on specific node ports.

**Scenario:**  
Use a LoadBalancer for public access, such as hosting a web app, and NodePort for testing or internal traffic.

---

