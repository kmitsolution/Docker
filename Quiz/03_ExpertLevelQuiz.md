
## **1. Which of the following namespaces Docker uses to isolate process IDs?**

A. mnt
B. pid
C. uts
D. net

---

## **2. Which cgroup subsystem controls CPU shares for a container?**

A. blkio
B. cpu
C. memory
D. freezer

---

## **3. What is the main purpose of `docker build --target`?**

A. Clean temporary layers
B. Build a specific stage in a multi-stage build
C. Deploy the image
D. Extract metadata from image

---

## **4. What does Docker's overlay2 storage driver *mainly* optimize?**

A. Kernel performance
B. Image layering and copy-on-write efficiency
C. Network routing
D. Log compression

---

## **5. Which Dockerfile instruction is executed at runtime, not during image build?**

A. RUN
B. COPY
C. ENTRYPOINT
D. ADD

---

## **6. In Docker networking, the bridge network provides which routing mechanism?**

A. Host-only NAT
B. Direct host IP exposure
C. Built-in DNS server and NAT
D. VLAN trunking

---

## **7. The root filesystem of a Docker container consists of what?**

A. A full VM disk
B. A union filesystem combining readonly layers + writable top layer
C. Only a writable layer
D. A RAM-only filesystem

---

## **8. What does `docker run --network=host` do?**

A. Creates a virtual NIC
B. Shares the container’s IP with other containers
C. Makes container use the host’s network namespace
D. Blocks external access

---

## **9. Which command removes **dangling** images only?**

A. `docker image prune`
B. `docker system prune`
C. `docker prune dangling`
D. `docker rmi --unused`

---

## **10. What happens when a Docker image layer is reused?**

A. It speeds up build due to caching
B. It increases image size
C. It invalidates previous layers
D. It forces rebuild of all layers

---

## **11. What is the primary benefit of Docker BuildKit?**

A. Faster builds, parallel execution, and better caching
B. Replaces Docker Hub
C. Manages container networking
D. Encrypts images by default

---

## **12. What does the Dockerfile instruction `HEALTHCHECK` do?**

A. Restarts container automatically
B. Runs a command to check container health status
C. Reduces memory usage
D. Ensures debugging output

---

## **13. In rootless Docker, which component runs without root privileges?**

A. Docker Engine
B. Kernel
C. Storage driver
D. All containers

---

## **14. What is the main reason to avoid `ADD` in favor of `COPY`?**

A. ADD does not work with tar files
B. ADD performs implicit extraction and remote URL fetch
C. COPY is slower
D. ADD cannot handle directories

---

## **15. When using bind mounts, which of the following is TRUE?**

A. Data is stored inside Docker internal storage
B. Performance depends on the host filesystem
C. Bind mounts are read-only
D. Bind mounts increase image size

---

# ✅ **Answers**

1 — B
2 — B
3 — B
4 — B
5 — C
6 — C
7 — B
8 — C
9 — A
10 — A
11 — A
12 — B
13 — D
14 — B
15 — B

---
