---

# **Docker MCQ – Intermediate Level**

## **1. Which of the following best describes a Docker image layer?**

A. A snapshot of the OS kernel
B. A read-only filesystem layer
C. A layer that stores logs
D. A temporary runtime layer

---

## **2. What happens when you run `docker run -p 8080:80 nginx`?**

A. Exposes container port 8080 to host port 80
B. Exposes host port 8080 to container port 80
C. Exposes both container and host ports
D. Blocks port access

---

## **3. What is the purpose of the `.dockerignore` file?**

A. To specify which images to ignore
B. To ignore certain files during image build
C. To avoid running containers
D. To prevent Docker from starting

---

## **4. Which Dockerfile instruction does *not* create a new layer?**

A. RUN
B. COPY
C. CMD
D. ADD

---

## **5. What does the `ENTRYPOINT` directive do?**

A. Specifies a default command that cannot be overridden
B. Stops a container
C. Installs system dependencies
D. Removes environment variables

---

## **6. What is a multi-stage Docker build used for?**

A. Running multiple containers
B. Reducing image size
C. Increasing build time
D. Enabling GUI applications

---

## **7. Which command removes **unused** containers, networks, and images?**

A. `docker remove all`
B. `docker prune all`
C. `docker system prune`
D. `docker clean`

---

## **8. What does the command `docker exec -it container bash` do?**

A. Starts a new container
B. Opens an interactive shell inside the container
C. Shows logs
D. Restarts the container

---

## **9. Which networking mode allows containers to share the host’s IP?**

A. None
B. Bridge
C. Host
D. Overlay

---

## **10. Overlay networks are used primarily in:**

A. Pure Linux systems
B. Docker Swarm
C. Kubernetes
D. Local containers

---

## **11. Which filesystem format does Docker use for images by default on Linux?**

A. ext4
B. ZFS
C. AUFS / OverlayFS
D. BTRFS

---

## **12. The `docker inspect` command returns:**

A. Container logs
B. Image layers
C. Detailed metadata in JSON
D. Docker events

---

## **13. Which command lists volumes?**

A. `docker volume list`
B. `docker list volume`
C. `docker volumes`
D. `docker volume ls`

---

## **14. What is the primary purpose of Docker Swarm?**

A. Logging
B. Load testing
C. Container orchestration
D. Authentication

---

## **15. In Docker Compose, the `depends_on` field ensures:**

A. Container health checks
B. Order of container startup
C. Resource limits
D. Network isolation

---

# **Answers**

1 — B
2 — B
3 — B
4 — C (CMD creates no layer)
5 — A
6 — B
7 — C
8 — B
9 — C
10 — B
11 — C
12 — C
13 — D
14 — C
15 — B

---


