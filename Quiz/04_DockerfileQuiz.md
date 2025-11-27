# 🐳 **Dockerfile MCQ Quiz**

## **1. Which instruction sets the base image for a Dockerfile?**

A. RUN
B. FROM
C. BASE
D. IMAGE

---

## **2. Which Dockerfile instruction executes commands *during the build process*?**

A. CMD
B. ENTRYPOINT
C. RUN
D. EXEC

---

## **3. Which instruction copies files from the host into the image?**

A. ADD
B. COPY
C. IMPORT
D. PUT

---

## **4. Which instruction defines the default command executed when a container starts?**

A. ENTRYPOINT
B. RUN
C. CMD
D. START

---

## **5. Which Dockerfile instruction does **not** create a new layer?**

A. RUN
B. COPY
C. ADD
D. ENTRYPOINT

---

## **6. What is the main advantage of multi-stage builds?**

A. Faster builds
B. Smaller final images
C. Easier logging
D. Automatic updates

---

## **7. Which instruction sets environment variables?**

A. LABEL
B. ARG
C. ENV
D. VAR

---

## **8. The difference between ARG and ENV is:**

A. ARG is available only at build time
B. ENV is available only during build
C. ARG overrides ENV
D. ARG is stored permanently

---

## **9. What is the purpose of `.dockerignore` in a Dockerfile context?**

A. Ignore certain file types when running a container
B. Exclude files from being sent to the build context
C. Stop Dockerfile execution
D. Log ignored layers

---

## **10. What happens if both ENTRYPOINT and CMD are defined?**

A. CMD overrides ENTRYPOINT completely
B. ENTRYPOINT overrides CMD completely
C. CMD provides default arguments to ENTRYPOINT
D. Both are ignored

---

## **11. Which instruction should you prefer when copying local files?**

A. ADD
B. COPY
C. MOVE
D. IMPORT

---

## **12. Which instruction defines metadata key-value pairs?**

A. TAG
B. INFO
C. LABEL
D. META

---

## **13. What is the effect of using `RUN apt-get update && apt-get install` in separate RUN instructions?**

A. Faster build
B. Smaller image
C. Larger image due to multiple layers
D. No difference

---

## **14. Which instruction is used for exposing ports as documentation?**

A. EXPOSE
B. PORT
C. OPEN
D. EXPORT

---

## **15. When should `ENTRYPOINT ["executable"]` be preferred?**

A. When the user must always run the command
B. When flexible override of command is needed
C. When no parameters are needed
D. When no image layering is required

---

## **16. What is the BuildKit feature that allows caching dependencies?**

A. `--cache-store`
B. `--mount=type=cache`
C. `--save-cache`
D. `--persist`

---

## **17. Which instruction changes the current working directory?**

A. CD
B. WORKDIR
C. PATH
D. SETDIR

---

## **18. Which instruction is used to include build-time secrets?**

A. SECRET
B. ARG SECRET
C. `RUN --mount=type=secret`
D. HIDE

---

## **19. What happens if multiple `FROM` instructions are used?**

A. Error—only one FROM allowed
B. Each FROM starts a new build stage
C. Only the last FROM is used
D. Docker merges the images

---

## **20. What is the recommended practice for reducing image size?**

A. Use many RUN instructions
B. Use minimal base images
C. Use ADD instead of COPY
D. Not using .dockerignore

---

# ✅ **Answers**

1 — B
2 — C
3 — B
4 — C
5 — D
6 — B
7 — C
8 — A
9 — B
10 — C
11 — B
12 — C
13 — C
14 — A
15 — A
16 — B
17 — B
18 — C
19 — B
20 — B

---
