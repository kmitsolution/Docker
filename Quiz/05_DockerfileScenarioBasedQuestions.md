# 🐳 **Dockerfile Scenario-Based Questions**

---

## **1. Scenario: Large Final Image**

Your Dockerfile installs dependencies like this:

```dockerfile
FROM ubuntu:latest
RUN apt-get update
RUN apt-get install -y python3 python3-pip
COPY . /app
```

Your final image size becomes very large.
**Question:** What changes should you make to reduce image size?

### ✅ **Answer:**

* Use a smaller base image, e.g. `python:3.10-slim` or `ubuntu:22.04-minimal`
* Combine RUN commands to reduce layers:

```dockerfile
RUN apt-get update && apt-get install -y python3 python3-pip && rm -rf /var/lib/apt/lists/*
```

* Remove unnecessary build files using `.dockerignore`

---

## **2. Scenario: Cached Layers Not Used**

You changed only one line in your app code, but Docker rebuilds many layers unnecessarily.

### ❓ **Question:**

How do you optimize your Dockerfile to maximize caching?

### ✅ **Answer:**

* Copy dependency files first:

```dockerfile
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
```

* Avoid copying the entire context early in the Dockerfile
* Add `.dockerignore` to exclude logs, .git, and temp files

---

## **3. Scenario: ENTRYPOINT Not Working as Expected**

Your Dockerfile has:

```dockerfile
ENTRYPOINT ["python3"]
CMD ["app.py"]
```

Running the container like:
`docker run image-name --version`
prints nothing.

### ❓ **Why does it fail and how do you fix it?**

### ✅ **Answer:**

EntryPoint forces Python to run, so `--version` is passed as argument to Python, not your script.

Fix by making your ENTRYPOINT your script launcher:

```dockerfile
ENTRYPOINT ["python3", "app.py"]
```

Or use ENTRYPOINT/CMD correctly depending on flexibility needed.

---

## **4. Scenario: Permissions Issues**

Your app fails with permission denied (`EACCES`) when running in container.
Dockerfile:

```dockerfile
FROM python:3.10
COPY . /app
WORKDIR /app
CMD ["python", "main.py"]
```

### ❓ **What’s missing?**

### ✅ **Answer:**

You’re running everything as root.
You need a non-root user:

```dockerfile
RUN useradd -m appuser
USER appuser
```

Also ensure files copied have correct permissions.

---

## **5. Scenario: Build Fails on COPY**

You see error:

```
COPY failed: no source files were specified
```

### ❓ **What's the common cause?**

### ✅ **Answer:**

Files are not in the build context.
Fix: run build from correct directory:

```
docker build -t app .
```

Or adjust COPY path.

---

## **6. Scenario: Slow Builds**

Build takes too long due to dependency installation.

### ❓ **How do you improve speed?**

### ✅ **Answer:**

* Use BuildKit for parallel builds:

```
DOCKER_BUILDKIT=1 docker build .
```

* Cache dependencies using:

```dockerfile
RUN --mount=type=cache,target=/root/.cache/pip pip install -r requirements.txt
```

* Use multi-stage builds
* Optimize COPY order

---

## **7. Scenario: Secret Keys Leaking**

You use environment variables for secrets:

```dockerfile
ENV API_KEY=123456
```

This gets exposed in the image history.

### ❓ **How do you fix it?**

### ✅ **Answer:**

Use BuildKit secrets:

```dockerfile
RUN --mount=type=secret,id=mysecret \
    sh -c 'export API_KEY=$(cat /run/secrets/mysecret)'
```

Or pass secrets at runtime using `docker run -e`.

---

## **8. Scenario: Application Requires Compile Tools**

You need tools like gcc to compile dependencies, but final image must be minimal.

### ❓ **What Docker feature solves this?**

### ✅ **Answer: Multi-stage builds**

Example:

```dockerfile
FROM gcc:latest AS builder
WORKDIR /app
COPY . .
RUN make

FROM alpine:latest
COPY --from=builder /app/app /usr/local/bin/
```

---

## **9. Scenario: The Container Ignores CMD**

Your Dockerfile has:

```dockerfile
ENTRYPOINT ["bash"]
CMD ["script.sh"]
```

Running container just opens bash without executing script.

### ❓ **How do you fix this?**

### ✅ **Answer:**

Pass CMD to ENTRYPOINT:

```dockerfile
ENTRYPOINT ["bash", "-c"]
CMD ["./script.sh"]
```

---

## **10. Scenario: App Crashes at Startup**

Container exits immediately with code 0.
Your Dockerfile CMD:

```dockerfile
CMD ["python", "-c", "print('done')"]
```

### ❓ **Why does container exit?**

### ✅ **Answer:**

Container stops when the main process ends.
Solutions:

* Run a long-lived process
* Use something like a web server
* Or tail logs:

```dockerfile
CMD ["tail", "-f", "/dev/null"]
```

(Not recommended unless debugging)
