
## Key Features of Prometheus

### 1. **Key Features for Monitoring Metrics**
   - **Feature:** Prometheus stores metrics as time-series data, identified by metric names and key-value pairs (labels).
   - **Scenario:** A microservices-based e-commerce application tracks the latency of API responses using Prometheus. Metrics such as `http_request_duration_seconds` with labels like `method`, `status`, and `endpoint` help identify performance bottlenecks.

### 2. **Custom Application Metrics**
   - **Exposing Metrics:** Applications expose metrics by providing an HTTP endpoint (e.g., `/metrics`) that Prometheus scrapes.
   - **Scenario:** A custom Python application uses the Prometheus Python client library to expose metrics for monitoring memory usage and processing time.

---

## Prometheus Data Collection

### 3. **Type of Data Monitored**
   - Prometheus is designed to monitor **numerical time-series data** like CPU usage, memory consumption, and application latencies.

### 4. **Metric Components**
   - Metrics typically include:
     1. **Metric Name**
     2. **Labels**
     3. **Timestamps**
     4. **Values**
   - **Scenario:** A service exposes `http_requests_total` with labels for `method` and `status_code` to count incoming HTTP requests.

### 5. **Collection Mechanism**
   - Prometheus uses a **pull-based model** to scrape metrics from targets via HTTP endpoints.
   - **Scenario:** Prometheus periodically scrapes `/metrics` endpoints from multiple services running in a Kubernetes cluster.

---

## Observability Concepts

### 6. **Service Level Management**
   - **SLO (Service Level Objective):** Defines a reliability target, such as "99.9% of requests must complete within 100ms."
   - **SLI (Service Level Indicator):** Measures performance against the SLO, e.g., request latency.
   - **Scenario:** A payment gateway monitors SLIs like `latency < 200ms` and sets SLOs for compliance.

### 7. **Three Pillars of Observability**
   - Logs, metrics, and traces are the foundational pillars.
   - **Scenario:** A distributed application integrates Prometheus for metrics, Elasticsearch for logs, and Jaeger for tracing.

### 8. **Distributed Tracing**
   - Each span in tracing records the operation's start and end time, helping track performance across services.
   - **Scenario:** For a request passing through `Gateway -> Auth -> User -> Redis`, there are 4 spans.

---

## Prometheus Architecture and Components

### 9. **Alerting with Prometheus**
   - **Alertmanager Role:** Handles alerts triggered by Prometheus.
   - **Scenario:** Prometheus triggers an alert when CPU usage exceeds 80%, and Alertmanager sends notifications to Slack.

### 10. **Built-in Query Language (PromQL)**
   - PromQL is used to query metrics stored in Prometheus.
   - **Scenario:** Query `rate(http_requests_total[5m])` to analyze incoming HTTP requests per second over the last 5 minutes.

### 11. **Exporters**
   - Exporters collect metrics from third-party systems.
   - **Native Exporter:** Node Exporter for Linux systems.
   - **Scenario:** Node Exporter monitors server metrics like disk space and memory usage.

---

## Benefits and Use Cases

### 12. **Observability Benefits**
   - Enhanced debugging and performance optimization.
   - **Scenario:** A dynamic environment with auto-scaling services uses Prometheus to adaptively monitor resource utilization.

### 13. **Pull-Based Monitoring Benefits**
   - Secure and flexible as targets are only accessible by the Prometheus server.
   - **Scenario:** Prometheus monitors microservices in an isolated network without exposing metrics endpoints publicly.

### 14. **Service Discovery**
   - Dynamically finds and monitors targets.
   - **Scenario:** In Kubernetes, Prometheus uses service discovery to track new pods automatically.

---

## Advanced Concepts

### 15. **Time-Series Database**
   - Prometheus stores data in a custom time-series database optimized for high-performance queries.

### 16. **Dynamic Provisioning**
   - Automatically provisions storage for persistent data.
   - **Scenario:** Prometheus dynamically adjusts persistent volumes in Kubernetes based on storage class specifications.

### 17. **CSI (Container Storage Interface)**
   - Provides a standard for managing storage volumes.
   - **Scenario:** Kubernetes integrates with CSI to provision storage dynamically for Prometheus' long-term storage.

---

## FAQ

### 18. **What triggers an alert in Prometheus?**
   - Alerts are triggered when a defined condition in the alert rules is met.

### 19. **What happens to short-lived jobs?**
   - Prometheus uses the Pushgateway to temporarily store metrics from short-lived jobs.
   - **Scenario:** A batch job pushes metrics to the Pushgateway before terminating.

### 20. **What is the purpose of traces?**
   - Traces help understand the flow of requests through a system.

### 21. **SLA vs. SLO**
   - **SLA (Service Level Agreement):** A contractual guarantee with penalties for violations.
   - **SLO (Service Level Objective):** Internal reliability goals.

---
