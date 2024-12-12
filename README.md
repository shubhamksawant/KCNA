# Kubernetes Questions and Scenarios: README Guide

## 1. **In a Kubernetes definition file, how is the `metadata` field typically defined?**
The `metadata` field provides information about the object, such as its name, labels, and namespace.
```yaml
metadata:
  name: example-pod
  namespace: default
  labels:
    app: my-app
```
**Scenario:** Assign meaningful labels to identify and organize resources for easier selection and filtering.

## 2. **How can you view the list of created deployments in Kubernetes?**
Use the following command:
```bash
kubectl get deployments
```
**Scenario:** To check deployments in a specific namespace, use `-n <namespace>`.

## 3. **How can you create a pod in Kubernetes using a YAML file named `pod-definition.yml`?**
Run:
```bash
kubectl apply -f pod-definition.yml
```
**Scenario:** Automate pod creation in CI/CD pipelines by storing YAML files in version control.

## 4. **By default, when a Docker container is deployed within a pod, how can users access the application?**
Users access the application via the pod’s IP address or by exposing it through a service.
**Scenario:** Use a ClusterIP or NodePort service to expose applications within or outside the cluster.

## 5. **In which Kubernetes namespace are the resources created that should be made available to all users?**
The `default` namespace.
**Scenario:** For shared resources like config maps or secrets, use `kube-system` or custom namespaces for better isolation.

## 6. **When scaling an application in Kubernetes to handle increased user load, how are additional instances typically created?**
Scale deployments using:
```bash
kubectl scale deployment <deployment-name> --replicas=<number>
```
**Scenario:** Use Horizontal Pod Autoscaler (HPA) for automatic scaling based on resource utilization.

## 7. **What is the smallest object that can be created in Kubernetes?**
The Pod.
**Scenario:** Deploy a single containerized application directly as a pod during initial testing.

## 8. **How can you view the created ReplicaSet in Kubernetes?**
Run:
```bash
kubectl get replicasets
```
**Scenario:** View ReplicaSet details to troubleshoot issues with scaling or pod creation.

## 9. **In a Kubernetes definition file, the `kind` field is used to specify:**
The type of resource being defined, such as `Pod`, `Deployment`, or `Service`.

## 10. **What is the primary role of controllers in Kubernetes?**
Controllers manage the desired state of objects, ensuring the cluster matches the configuration defined.
**Scenario:** Use the Deployment controller to ensure specified replicas are always running.

## 11. **How do you apply changes to a modified Kubernetes deployment object using a definition file called `deployment-def.yml`?**
Run:
```bash
kubectl apply -f deployment-def.yml
```

## 12. **What is the role of a ReplicaSet in Kubernetes?**
ReplicaSets maintain the desired number of pod replicas and replace failed ones.

## 13. **What is the correct API version to use in the replication controller definition file?**
Use `apiVersion: v1`.

## 14. **What command can you use to update the image of your application in a Kubernetes deployment without modifying the deployment definition file?**
Run:
```bash
kubectl set image deployment/<deployment-name> <container-name>=<image>
```
**Scenario:** Update a backend service image to deploy the latest bug fixes.

## 15. **Why does a ReplicaSet require a selector definition, even if the pod definition is provided in the template?**
The selector ensures the ReplicaSet can identify and manage the correct pods.

## 16. **What is the advantage of having multiple containers within the same pod in Kubernetes?**
Containers in the same pod share resources and enable sidecar patterns for logging, caching, etc.

## 17. **What is the recommended approach for expanding the physical capacity of a Kubernetes cluster when the current node lacks sufficient capacity?**
Add a new node to the cluster.
**Scenario:** Use cloud-based auto-scaling groups to provision nodes dynamically.

## 18. **What is the purpose of a Deployment in Kubernetes?**
To manage pod scaling, updates, and rollbacks.

## 19. **Why is the use of a replication controller important in Kubernetes?**
It ensures a specified number of pod replicas are always running.

## 20. **You want to create a pod in the `dev` namespace instead of the default namespace using a YAML manifest file called `pod-def.yml`. Which command should you use to achieve this?**
Run:
```bash
kubectl apply -f pod-def.yml -n dev
```

## 21. **To list pods in the `kube-system` namespace, which command should you use?**
Run:
```bash
kubectl get pods -n kube-system
```

## 22. **How can you update the number of replicas in a replica set using the kubectl scale command?**
Run:
```bash
kubectl scale replicaset <replica-set-name> --replicas=<number>
```

## 23. **How can you view the history and revisions of a deployment rollout in Kubernetes?**
Run:
```bash
kubectl rollout history deployment/<deployment-name>
```
**Scenario:** Use the command to identify and rollback to stable versions during deployment failures.

## 24. **Why are deployment rollouts and revisions important in Kubernetes?**
They allow tracking changes and reverting to a stable state when issues occur.

## 25. **Regardless of the approach used to create an object in Kubernetes, what does Kubernetes use to store information about the object internally?**
Kubernetes uses **etcd**, a distributed key-value store.

## 26. **How can you update a replica set to scale from 3 replicas to 6 replicas?**
Run:
```bash
kubectl scale rs <replica-set-name> --replicas=6
```

## 27. **When using the kubectl apply command in Kubernetes, which of the following sources does it consider before deciding what changes to make?**
It compares the local file with the cluster’s last applied configuration.

## 28. **In Kubernetes, which namespace is automatically created by Kubernetes when the cluster is first set up?**
The `kube-system` namespace.

## 29. **Which API version would you typically use when creating a Pod object in a Kubernetes definition file?**
Use `apiVersion: v1`.

## 30. **How can you switch to a specific namespace permanently in Kubernetes, so that you don't have to specify the namespace option each time you run a command?**
Set the namespace context:
```bash
kubectl config set-context --current --namespace=<namespace>
```

## 31. **How can you create a new namespace in Kubernetes?**
Run:
```bash
kubectl create namespace <namespace-name>
```

## 32. **What parameter is used with the `kubectl run` command to specify the application image when deploying a Docker container as a pod?**
Use the `--image` parameter to specify the application image.

```bash
kubectl run <pod-name> --image=<image-name>
```

Example:
```bash
kubectl run my-pod --image=nginx
```

---

## 33. **Why is it beneficial to use labels in Kubernetes when deploying multiple pods?**
Labels allow for:
1. **Organization**: Grouping resources logically (e.g., all pods related to a specific app).
2. **Selection**: Simplifies the use of selectors in services, ReplicaSets, and deployments.
3. **Management**: Enables filtering and bulk operations on resources.

Example:
```yaml
labels:
  app: web
  tier: frontend
```

---

## 34. **How can you rollback a Kubernetes deployment to a previous revision?**
Use the following command:
```bash
kubectl rollout undo deployment/<deployment-name>
```
To rollback to a specific revision:
```bash
kubectl rollout undo deployment/<deployment-name> --to-revision=<revision-number>
```

---

## 35. **In a Kubernetes definition file, why is the "containers" property within the "spec" section defined as a list or an array?**
The `containers` property supports multiple containers within a pod, enabling patterns like sidecar or ambassador.

Example:
```yaml
spec:
  containers:
  - name: main-app
    image: nginx
  - name: sidecar
    image: busybox
```

---

## 36. **Which of the following fields are required in a Kubernetes definition file?**
Typically required fields are:
1. **apiVersion**: Defines the Kubernetes API version.
2. **kind**: Specifies the type of resource (e.g., Pod, Deployment).
3. **metadata**: Includes name and labels.
4. **spec**: Configuration details.

Example:
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
spec:
  containers:
  - name: nginx
    image: nginx
```

---

## 37. **Which approach is used to specify what actions should be performed in Kubernetes without specifying how they should be executed?**
The declarative approach. Users describe the desired state of the system, and Kubernetes ensures this state.

---

## 38. **To connect a web-app pod in the default namespace to a service named "db-service" in the "dev" namespace, what is the correct hostname format?**
The hostname format is:
```
<service-name>.<namespace>.svc.cluster.local
```
For this example:
```
db-service.dev.svc.cluster.local
```

---

## 39. **When using the `kubectl apply` command to create an object in Kubernetes, what happens to the YAML version of the local object config file?**
The configuration is applied to the cluster and stored as the "last-applied-configuration" annotation.

---

## 40. **When using a replication controller in Kubernetes, how can you specify the number of replicas (instances) of a pod that should be running?**
Specify the replicas in the YAML file or use the `--replicas` flag:
```yaml
spec:
  replicas: 3
```
Command:
```bash
kubectl scale rc <replication-controller-name> --replicas=3
```

---

## 41. **When you create a deployment in Kubernetes, what additional objects are automatically created alongside the deployment?**
A **ReplicaSet** is created to manage the pods.

---

## 42. **How can you check the status of a deployment rollout in Kubernetes?**
Use:
```bash
kubectl rollout status deployment/<deployment-name>
```

---

## 43. **What is the default deployment strategy in Kubernetes where the application never goes down during the update?**
The **RollingUpdate** strategy ensures zero downtime.

---

## 44. **How does a ReplicaSet know which pods to monitor?**
Through label selectors defined in its `spec.selector` field.

Example:
```yaml
spec:
  selector:
    matchLabels:
      app: my-app
```

---

## 45. **When a new deployment is created, what is the result of the rollout process?**
The deployment creates a new ReplicaSet, which in turn creates the required pods.

---

## 46. **What does the `kubectl apply` command do in the declarative approach of managing objects in Kubernetes?**
It:
1. Creates resources if they do not exist.
2. Updates resources if they already exist, based on changes in the YAML file.

---

## 47. **What is the purpose of assigning quotas to Kubernetes namespaces?**
Quotas ensure resource limits, preventing one namespace from monopolizing cluster resources.

Example:
```yaml
apiVersion: v1
kind: ResourceQuota
metadata:
  name: resource-limits
  namespace: dev
spec:
  hard:
    cpu: "4"
    memory: "16Gi"
```

---

## 48. **What command would you use to view the list of created replication controllers in Kubernetes?**
```bash
kubectl get rc
```

---

## 49. **Why would you create separate namespaces for dev and production environments in Kubernetes?**
1. **Isolation**: Prevents interference between environments.
2. **Resource Quotas**: Allocates resources specific to environments.
3. **Access Control**: Facilitates RBAC policies.

---

## 50. **Which namespace in Kubernetes is created at cluster startup and contains internal services required for networking and DNS?**
The `kube-system` namespace.

---

## 51. **How can you view pods in all namespaces in Kubernetes?**
```bash
kubectl get pods --all-namespaces
```

---

## 52. **What are the two strategies for making deployments in Kubernetes?**
1. **Recreate**: Terminates old pods before creating new ones.
2. **RollingUpdate**: Gradually updates pods to avoid downtime.

---

## 53. **To view all the objects created after a deployment, which command can you use?**
```bash
kubectl get all
```

---

## 54. **How can you view detailed information about a specific pod named "my-app-pod" in Kubernetes?**
```bash
kubectl describe pod my-app-pod
```

---

## 55. **How can you limit resources in a namespace in Kubernetes?**
By creating a `ResourceQuota` object.

---

## 56. **Why is the "last applied configuration" feature useful in Kubernetes?**
It helps in auditing changes and reverting configurations during troubleshooting.

---

## 57. **Why is the template section required in the replica set specification, even if there are existing pods with matching labels?**
The template defines how new pods should be created, ensuring consistent configurations.

