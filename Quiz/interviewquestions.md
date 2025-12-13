
## Docker – Intermediate Questions with Answers (1–7)

### 1. What is the difference between a Docker image and a Docker container?

**Answer:**
A **Docker image** is a read-only template that contains application code, dependencies, and instructions. A **Docker container** is a running instance of that image. Internally, a container adds a **writable layer** on top of the image layers, allowing runtime changes without modifying the image.

---

### 2. What happens when you run `docker run`?

**Answer:**
When `docker run` is executed:

1. Docker checks if the image exists locally; if not, it pulls it from a registry.
2. It creates a container by adding a writable layer on top of the image.
3. It sets up networking, storage, and namespaces.
4. It applies resource limits using cgroups.
5. It starts the container process defined by `ENTRYPOINT` or `CMD`.

---

### 3. How does Docker layering work?

**Answer:**
Each instruction in a Dockerfile creates a **layer**. Layers are cached and reused across images. This improves build speed and reduces storage usage. Ordering instructions correctly (e.g., installing dependencies before copying code) helps maximize cache efficiency.

---

### 4. Difference between `CMD` and `ENTRYPOINT`?

**Answer:**

* `ENTRYPOINT` defines the main executable and is rarely overridden.
* `CMD` provides default arguments that can be overridden at runtime.

Using both together allows flexible containers, such as defining a fixed command with variable parameters.

---

### 5. Difference between Docker volumes and bind mounts?

**Answer:**

* **Volumes** are managed by Docker and stored in Docker’s internal directory. They are portable and preferred for production.
* **Bind mounts** map a host directory to a container and depend on host filesystem structure, making them suitable for development.

---

### 6. What are namespaces and cgroups?

**Answer:**

* **Namespaces** isolate resources like process IDs, networks, and filesystems.
* **cgroups** control and limit resource usage like CPU and memory.

Together, they provide isolation and resource management for containers.

---

### 7. How do you reduce Docker image size?

**Answer:**

* Use minimal base images (e.g., `alpine`)
* Use multi-stage builds
* Combine RUN commands
* Remove unnecessary packages and cache files
* Avoid copying unused files

---

## Kubernetes – Intermediate Questions with Answers (8–15)

### 8. Difference between a Pod and a Deployment?

**Answer:**
A **Pod** is the smallest unit in Kubernetes and runs one or more containers. A **Deployment** manages Pods and provides scaling, rolling updates, and self-healing. In production, Deployments are preferred to ensure availability and resilience.

---

### 9. Role of kube-apiserver?

**Answer:**
The **kube-apiserver** is the central control point of the cluster. All components (kubectl, scheduler, controllers) communicate through it. It validates requests, updates cluster state, and persists data in etcd.

---

### 10. How does Kubernetes handle service discovery?

**Answer:**
Kubernetes uses **Services** and **DNS**. Each Service gets a stable IP and DNS name. Traffic is load-balanced across matching Pods using kube-proxy and iptables or IPVS.

---

### 11. Difference between ConfigMap and Secret?

**Answer:**

* **ConfigMaps** store non-sensitive configuration data.
* **Secrets** store sensitive data like passwords and tokens (base64-encoded).

Secrets are more secure and can be integrated with external secret managers.

---

### 12. How do rolling updates and rollbacks work?

**Answer:**
During a rolling update, Kubernetes gradually replaces old Pods with new ones while maintaining availability. If a failure occurs, Kubernetes can rollback to a previous ReplicaSet using stored revision history.

---

### 13. What happens when a Pod or node fails?

**Answer:**

* If a **Pod crashes**, the controller restarts or recreates it.
* If a **node fails**, Kubernetes reschedules Pods to healthy nodes.

This ensures high availability through self-healing mechanisms.

---

### 14. Liveness vs Readiness probes?

**Answer:**

* **Liveness probe** checks if the container should be restarted.
* **Readiness probe** checks if the container is ready to receive traffic.

They help avoid downtime and prevent traffic to unhealthy Pods.

---

### 15. Difference between ClusterIP, NodePort, and LoadBalancer?

**Answer:**

* **ClusterIP**: Internal access only (default).
* **NodePort**: Exposes service on each node’s IP and port.
* **LoadBalancer**: Uses a cloud provider’s external load balancer.

ClusterIP is used for internal services, NodePort for testing, and LoadBalancer for production external access.
