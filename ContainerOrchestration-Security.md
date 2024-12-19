

# **Kubernetes Security Q&A with Scenarios**

### **1. Which of the following statements is true regarding service accounts in Kubernetes version 1.24?**
**Answer**: Kubernetes version 1.24 disables the automatic mounting of service account tokens to pods by default for security reasons.  

**Scenario**:  
If a pod in a namespace uses a service account, you now need to explicitly configure the token mount using:  
```yaml
automountServiceAccountToken: true
```  
in the pod definition.

---

### **2. What is the relationship between the secret object and the service account in Kubernetes?**
**Answer**: Secrets are used to store service account tokens. A service account in Kubernetes automatically creates a secret object containing the token for API access.

**Example**: To link a specific secret:  
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: pod-with-secret
spec:
  serviceAccountName: my-service-account
  automountServiceAccountToken: true
```

---

### **3. Which feature can be used to restrict access between the pods in a cluster?**
**Answer**: Kubernetes **Network Policies** can be used to restrict access between pods.

**Scenario**: To deny all ingress traffic except from a specific namespace:
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: deny-all-except-ns
spec:
  podSelector: {}
  ingress:
    - from:
        - namespaceSelector:
            matchLabels:
              name: allowed-namespace
```

---

### **4. What is the purpose of a ClusterRoleBinding object in Kubernetes?**
**Answer**: A ClusterRoleBinding grants permissions to users, groups, or service accounts to access cluster-wide resources.

**Example**:  
```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: cluster-admin-binding
subjects:
- kind: User
  name: jane.doe
roleRef:
  kind: ClusterRole
  name: cluster-admin
  apiGroup: rbac.authorization.k8s.io
```

---

### **5. If you create a cluster role for namespaced resources, what access do the users get?**
**Answer**: Users will only get access to the namespaced resources across all namespaces.

---

### **6. Which of the following resources belong to the "apps" subgroup in Kubernetes?**
**Answer**: Resources like `deployments`, `statefulsets`, and `daemonsets` belong to the "apps" subgroup.

---

### **7. What command can be used to view the contents of a secret object in Kubernetes?**
**Answer**:  
```bash
kubectl get secret <secret-name> -o yaml
```

---

### **8. Which of the following is true about the format of the sections in the kubeconfig file?**
**Answer**: Kubeconfig files are YAML-based and consist of `clusters`, `users`, and `contexts` sections.

---

### **9. Which of the following sections are included in the kubeconfig file?**
**Answer**: The sections include:
- `clusters`  
- `contexts`  
- `users`  
- `current-context`  

---

### **10. Which of the following statements is true about using KubeConfig in kubectl?**
**Answer**: The `KUBECONFIG` environment variable or the `--kubeconfig` flag can be used to specify a custom kubeconfig file.

---

### **11. What field can you use to allow access to specific resources alone in Kubernetes?**
**Answer**: Use the **"resources"** field in a Role or ClusterRole definition.

**Example**:  
```yaml
rules:
- apiGroups: ["apps"]
  resources: ["deployments"]
  verbs: ["get", "list"]
```

---

### **12. In Kubernetes, how are resources categorized based on their scope?**
**Answer**: Resources are categorized as:
1. **Namespaced**: Resources like Pods, Services, ConfigMaps.
2. **Cluster-scoped**: Resources like Nodes, PersistentVolumes.

---

### **13. What API version and kind do you need to set to create a role object in Kubernetes using a role definition file?**
**Answer**:  
- **API version**: `rbac.authorization.k8s.io/v1`  
- **Kind**: `Role`

**Example**:  
```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  name: pod-reader
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "list"]
```

---

### **14. What command can you use to log in to your private Docker registry?**
**Answer**:  
```bash
docker login <registry-url>
```

---

### **15. What is the purpose of Kube Proxy in a Kubernetes cluster?**
**Answer**: Kube Proxy manages network communication for pods, providing load balancing and forwarding traffic between services.

---

### **16. Which of the following solutions support Kubernetes network policies?**
**Answer**: Solutions like **Calico**, **Weave**, and **Cilium** support Kubernetes Network Policies.

---

### **17. What is used to authorize users to cluster-wide resources like nodes and persistent volumes in Kubernetes?**
**Answer**: **ClusterRoles** and **ClusterRoleBindings** are used to authorize access to cluster-wide resources.

---

### **18. What format is used to define a set of policies in Attribute-Based Authorization?**
**Answer**: Policies are defined in a JSON or YAML format.

---

### **19. In a Kubernetes cluster, if you want to view the roles defined within a specific namespace, which command should you use?**
**Answer**:  
```bash
kubectl get roles --namespace=<namespace>
```

---

### **20. Who is authorized by the node authorizers to make requests to kube-apiserver?**
**Answer**: **Kubelet nodes** are authorized to make requests to the kube-apiserver.


## **1. Docker Image Name Prefix**
**Question**: In the context of a Docker image name in a Kubernetes pod definition file, when the image name is provided without a prefix, what does the prefix usually represent, and what is the default value assumed if none is provided?

**Answer**: If no prefix is provided, the default registry prefix is assumed to be Docker Hub's "library" namespace. For example:

- **Image without prefix**: `nginx`
- **Default value assumed**: `docker.io/library/nginx`

**Scenario**:
When you deploy a Pod:
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
spec:
  containers:
    - name: nginx-container
      image: nginx  # Default prefix is docker.io/library/nginx
```
Kubernetes automatically resolves it to `docker.io/library/nginx`.

---

## **2. Editing Service Account of an Existing Deployment**
**Question**: Can you edit the service account of an existing deployment in Kubernetes?

**Answer**: Yes, you can modify the `serviceAccountName` in the Deployment spec.

**Command**:
```bash
kubectl edit deployment <deployment-name>
```

**Scenario**:
Modify an existing Deployment to use a custom service account:
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-deployment
spec:
  template:
    spec:
      serviceAccountName: my-custom-sa
```

---

## **3. Network Policy Rules**
**Question**: Where do we build our network rules in a Kubernetes network policy definition file?

**Answer**: Network rules are specified under the `spec` section of the `NetworkPolicy` resource.

**Example**:
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-specific-ingress
spec:
  podSelector:
    matchLabels:
      role: frontend
  policyTypes:
    - Ingress
  ingress:
    - from:
        - podSelector:
            matchLabels:
              role: backend
```
Here, the rules define ingress access to `frontend` pods from `backend` pods.

---

## **4. Security Settings at Pod Level**
**Question**: When configuring security settings at the pod level, what happens to the settings?

**Answer**: Pod-level security settings apply to all containers within the Pod unless overridden at the container level.

**Example**:
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: secure-pod
spec:
  securityContext:
    runAsUser: 1000
    runAsGroup: 3000
  containers:
    - name: app-container
      image: nginx
      securityContext:
        runAsUser: 2000  # Overrides Pod-level setting
```
Here, `runAsUser: 2000` for the container overrides the Pod-level setting `runAsUser: 1000`.

---

## **5. Purpose of RoleBinding**
**Question**: What is the purpose of a RoleBinding object in Kubernetes?

**Answer**: A `RoleBinding` grants permissions defined in a Role to a user, group, or service account within a specific namespace.

**Example**:
```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: read-pods-binding
  namespace: default
subjects:
  - kind: User
    name: jane
    apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: Role
  name: read-pods
  apiGroup: rbac.authorization.k8s.io
```
Here, user `jane` is granted the permissions defined in the `read-pods` Role.

---

## **6. Viewing Role Details**
**Question**: What command should you use to view more details about a specific role in a Kubernetes cluster?

**Answer**:
```bash
kubectl describe role <role-name> -n <namespace>
```

**Scenario**:
To view details of a Role named `read-pods` in the `default` namespace:
```bash
kubectl describe role read-pods -n default
```

---

## **7. Clusters Section in Kubeconfig File**
**Question**: What does the clusters section contain in the kubeconfig file?

**Answer**: The `clusters` section defines the Kubernetes cluster endpoints, including the server URL and certificate information.

**Example**:
```yaml
clusters:
- cluster:
    certificate-authority-data: BASE64_ENCODED_CERT
    server: https://kubernetes.example.com
  name: my-cluster
```
- **`server`**: API server endpoint.
- **`certificate-authority-data`**: CA certificate data for secure communication.

---

## **8. Role-Based Access Control (RBAC)**
**Question**: What is Role-Based Access Control (RBAC)?

**Answer**: RBAC is a security mechanism in Kubernetes that allows administrators to define roles and permissions for users, groups, or service accounts.

**Core Components**:
1. **Role**: Defines permissions for a namespace.
2. **ClusterRole**: Defines cluster-wide permissions.
3. **RoleBinding**: Grants Role permissions to subjects.
4. **ClusterRoleBinding**: Grants ClusterRole permissions to subjects.

**Example**:
- Use RBAC to grant a user read-only access to a namespace.

---

## **9. Impersonation in Kubernetes**
**Question**: What command should you use to impersonate another user and check their permission to create deployments in a Kubernetes cluster?

**Answer**:
```bash
kubectl auth can-i create deployments --as=<username>
```

**Scenario**:
To check if user `jane` can create deployments:
```bash
kubectl auth can-i create deployments --as=jane
```

---

## **10. Kubernetes Network Policies**
**Question**: Which of the following statements is true about Kubernetes network policies?

**Answer**: Kubernetes network policies control the traffic flow between Pods at the network level. By default, all Pods can communicate with each other unless restricted by a network policy.

**Example**:
- Without a network policy, all communication is allowed.
- Once a policy is applied, only explicitly defined traffic is allowed.

---

## **11. Non-Namespaced Resources**
**Question**: Which command would you use to see a full list of non-namespaced resources in Kubernetes?

**Answer**:
```bash
kubectl api-resources --namespaced=false
```

**Output Example**:
```plaintext
NAME                              SHORTNAMES   APIGROUP                       NAMESPACED   KIND
nodes                             no           <none>                         false        Node
persistentvolumes                 pv           <none>                         false        PersistentVolume
```

---

## **12. Default Service Account**
**Question**: What is the default service account created for every namespace in Kubernetes?

**Answer**: The default service account is `default`. It is automatically created in every namespace.

**Command to list service accounts**:
```bash
kubectl get serviceaccounts -n <namespace>
```

**Example**:
```plaintext
NAME      SECRETS   AGE
default   1         1d
```

---

## **13. Security Context in Pod Spec**
**Question**: Which field should be added to the specs section of a pod in order to configure security context on a pod in Kubernetes?

**Answer**: The `securityContext` field should be used.

**Example**:
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: secure-pod
spec:
  securityContext:
    runAsUser: 1000
    runAsGroup: 3000
  containers:
    - name: app-container
      image: nginx
```


## **1. Characteristics of Tokens Generated by the Kubernetes Token Request API**  
**Answer:**  
- Tokens are short-lived with a configurable time-to-live (TTL).  
- They are bound to a specific audience (e.g., Kubernetes API server).  
- Signed by the cluster's certificate authority (CA).  
- Scoped to a particular namespace or service account.

**Scenario:**  
To generate a service account token with the API:  
```bash
kubectl create serviceaccount demo-sa
kubectl create token demo-sa --duration=10m
```
Here, the token will expire after 10 minutes.

---

## **2. If `ingress` is the only `policyTypes` in a Network Policy**  
**Answer:**  
The policy applies only to **incoming traffic** (Ingress). Outgoing (Egress) traffic remains unrestricted.

**Scenario:**  
A network policy to restrict ingress traffic:  
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-http
  namespace: default
spec:
  policyTypes:
  - Ingress
  podSelector:
    matchLabels:
      app: web
  ingress:
  - from:
    - podSelector:
        matchLabels:
          app: allowed
    ports:
    - protocol: TCP
      port: 80
```

---

## **3. Scope of Roles and RoleBindings**  
**Answer:**  
- Roles and RoleBindings are **namespace-scoped**.  
- ClusterRoles and ClusterRoleBindings are **cluster-scoped**.

**Scenario:**  
Creating a namespace-scoped role:  
```bash
kubectl create role pod-reader --verb=get,list,watch --resource=pods --namespace=default
```

Creating a cluster-scoped role:  
```bash
kubectl create clusterrole cluster-admin --verb=* --resource=*
```

---

## **4. Purpose of Docker Registry Secret Type in Kubernetes**  
**Answer:**  
Allows Kubernetes to authenticate and pull private container images.

**Scenario:**  
Creating a secret for DockerHub:  
```bash
kubectl create secret docker-registry my-secret \
  --docker-server=https://index.docker.io/v1/ \
  --docker-username=<username> \
  --docker-password=<password> \
  --docker-email=<email>
```

---

## **5. Command to Create a Service Account**  
**Answer:**  
```bash
kubectl create serviceaccount <service-account-name>
```

**Example:**  
```bash
kubectl create serviceaccount my-service-account
```

---

## **6. Difference Between Ingress and Egress Traffic**  
**Answer:**  
- **Ingress:** Traffic **entering** the pod.  
- **Egress:** Traffic **leaving** the pod.

**Scenario:**  
Restricting egress traffic using a NetworkPolicy:  
```yaml
policyTypes:
- Egress
egress:
- to:
  - ipBlock:
      cidr: 10.0.0.0/24
```

---

## **7. Field to Use a Service Account Other Than the Default**  
**Answer:**  
Add `serviceAccountName` in the pod specification:  
```yaml
serviceAccountName: custom-sa
```

**Example:**  
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: mypod
spec:
  serviceAccountName: my-service-account
  containers:
  - name: mycontainer
    image: nginx
```

---

## **8. Behavior of AlwaysDeny Authorization Mode**  
**Answer:**  
It denies all API requests **without checking permissions**.

**Scenario:**  
When testing cluster authorization restrictions, you can configure `--authorization-mode=AlwaysDeny` in the API server flags.

---

## **9. Resources in the Apps Subgroup of Kubernetes API**  
**Answer:**  
Resources include:  
- Deployments  
- StatefulSets  
- DaemonSets  
- ReplicaSets  

---

## **10. Users Section in Kubeconfig File**  
**Answer:**  
The `users` section defines user credentials, such as certificates, tokens, or keys, for authentication.

**Example:**  
```yaml
users:
- name: my-user
  user:
    token: <token>
```

---

## **11. Linking Network Policy to a Pod**  
**Answer:**  
Network Policies use `podSelector` to identify the target pods.  

**Example:**  
```yaml
podSelector:
  matchLabels:
    app: frontend
```

---

## **12. Namespaced Kubernetes Resources**  
**Answer:**  
Examples of namespaced resources:  
- Pods  
- Services  
- ConfigMaps  
- Secrets  
- Deployments  

---

## **13. Configuring Security Settings at Pod and Container Levels**  
**Answer:**  
- **Pod-level security settings:** Act as a baseline for all containers in the pod.  
- **Container-level security settings:** Override pod-level settings for that specific container.

**Scenario:**  
Pod-level security:  
```yaml
securityContext:
  runAsUser: 1000
```

Container-level security:  
```yaml
containers:
- name: app-container
  securityContext:
    runAsUser: 2000
```

---

## **14. Default Service Account in Kubernetes**  
**Answer:**  
Every namespace has a **default** service account named `default`.

**Command to list service accounts:**  
```bash
kubectl get serviceaccounts
```

---

## **15. Context Section in Kubeconfig File**  
**Answer:**  
Defines the cluster, user, and namespace to use.  

**Example:**  
```yaml
contexts:
- name: my-context
  context:
    cluster: my-cluster
    user: my-user
    namespace: my-namespace
```

---

## **16. Command to List Non-Namespaced Resources**  
**Answer:**  
```bash
kubectl api-resources --namespaced=false
```

---

## **17. Security Mechanism for Secure Communication**  
**Answer:**  
Kubernetes uses **TLS certificates** for secure communication between components like ETCD, API server, and nodes.

---

## **18. Command to List Kubernetes Namespaced Resources**  
**Answer:**  
```bash
kubectl api-resources --namespaced=true
```

---

## **19. Command to Change Current Context**  
**Answer:**  
```bash
kubectl config use-context <context-name>
```

---

## **20. Purpose of `library` in Image Names (e.g., library/nginx)**  
**Answer:**  
`library` indicates the **official Docker Hub image**. For example, `nginx` resolves to `library/nginx` by default.

---

## **21. List Service Accounts in Kubernetes Cluster**  
**Answer:**  
```bash
kubectl get serviceaccounts --all-namespaces
```


