
# 🐳 Docker CLI Commands (with Explanations)

---

## 📦 Build & Manage Images

### Build a Docker Image  
```bash
docker build -t <image_name> .
```
➡️ Builds a Docker image from the Dockerfile in the current directory.

### List Docker Images  
```bash
docker images
```
➡️ Lists all locally available Docker images.

### Pull an Image  
```bash
docker pull <image_name>
```
➡️ Downloads an image from Docker Hub or another registry.

### Remove a Docker Image  
```bash
docker rmi <image_id>
```
➡️ Removes a Docker image.

---

## 📦 Run & Manage Containers

### Run a Container  
```bash
docker run -d -p 8080:80 --name <container_name> <image_name>
```
➡️ Runs a container in detached mode, maps ports, and assigns a name.

### Show Running Containers  
```bash
docker ps
```
➡️ Displays currently running containers.

### Show All Containers  
```bash
docker ps -a
```
➡️ Displays all containers (running and stopped).

### Stop a Running Container  
```bash
docker stop <container_id>
```
➡️ Stops a running container.

### Start a Stopped Container  
```bash
docker start <container_id>
```
➡️ Starts a stopped container.

### Restart a Container  
```bash
docker restart <container_id>
```
➡️ Restarts a container.

### Remove a Stopped Container  
```bash
docker rm <container_id>
```
➡️ Removes a stopped container.

---

## 🐚 Access & Logs

### Open Terminal in a Container  
```bash
docker exec -it <container_id> /bin/bash
```
➡️ Opens an interactive terminal session inside a running container.

### View Container Logs  
```bash
docker logs <container_id>
```
➡️ Displays the logs of a container.

---

## 🧩 Docker Compose

### Start Multiple Containers  
```bash
docker-compose up
```
➡️ Starts multiple containers as defined in a `docker-compose.yml` file.

### Stop Multiple Containers  
```bash
docker-compose down
```
➡️ Stops multiple containers.

---

✅ **Notes:**
- `-d` → Run in **detached mode** (in background)  
- `-p 8080:80` → Map **port 8080 on your host** to **port 80 in the container**  
- `-it` → Interactive terminal  




---
# 📄 **All Dockerfile Commands**  
---


| Command         | What It Does | Example |
|-----------------|--------------|---------|
| **`FROM`**       | Specifies the base image | `FROM openjdk:17-jdk-slim` |
| **`WORKDIR`**    | Sets the working directory | `WORKDIR /app` |
| **`COPY`**       | Copies files/folders from host to container | `COPY ./src /app` |
| **`ADD`**        | Like `COPY`, but can fetch URLs/extract archives | `ADD https://example.com/file.zip /app/` |
| **`RUN`**        | Executes commands during build | `RUN npm install` |
| **`CMD`**        | Default command to run when container starts | `CMD ["java", "-jar", "app.jar"]` |
| **`ENTRYPOINT`** | Hard-coded executable (overrides `CMD`) | `ENTRYPOINT ["java", "-jar"]` |
| **`EXPOSE`**     | Declares container ports (informational) | `EXPOSE 8080` |
| **`ENV`**        | Sets environment variables | `ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk` |
| **`ARG`**        | Defines build-time variables | `ARG JAR_FILE=target/*.jar` |
| **`LABEL`**      | Adds metadata (e.g., maintainer) | `LABEL maintainer="you@example.com"` |
| **`USER`**       | Sets the user for subsequent commands | `USER appuser` |
| **`VOLUME`**     | Creates a persistent mount point | `VOLUME /data` |
| **`HEALTHCHECK`** | Configures container health checks | `HEALTHCHECK CMD curl -f http://localhost:8080` |
| **`ONBUILD`**    | Triggers instructions for child images | `ONBUILD COPY ./app/src` |
| **`STOPSIGNAL`** | Sets the signal to stop the container | `STOPSIGNAL SIGKILL` |
| **`SHELL`**      | Overrides the default shell | `SHELL ["/bin/bash", "-c"]` |

---