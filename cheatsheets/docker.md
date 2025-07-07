# Docker Cheatsheet

Useful Docker commands grouped by common tasks.

---

## ✅ Status & Info

```bash
# show running containers
docker ps

# show all containers (running and stopped)
docker ps -a

# list local images
docker images

# show Docker disk usage
docker system df

# list installed WSL distros (Windows only)
wsl --list --verbose
```

---

## 🚀 Run & Access

```bash
# start a container
docker start <container_id_or_name>

# stop a container
docker stop <container_id_or_name>

# open a shell in a running container
docker exec -it <container_id_or_name> bash

# view container logs (follow mode)
docker logs -f <container_id_or_name>

# run an interactive container (with shell)
docker run -it <image_name> bash

# run and map ports (host:container)
docker run -p 8080:80 <image_name>
```

---

## 🛠️ Build & Manage

```bash
# pull image from Docker Hub
docker pull <image_name>

# build image from Dockerfile
docker build -t <tag_name> .

# remove container
docker rm <container_id_or_name>

# remove image
docker rmi <image_id_or_name>
```

---

## 🧹 Cleanup & Uninstall

```bash
# remove stopped containers
docker container prune

# remove unused images
docker image prune -a

# remove orphaned volumes
docker volume prune

# remove everything not in use (containers, images, volumes, cache)
docker system prune -a --volumes

# remove a WSL distro (Windows only)
wsl --list --verbose
wsl --unregister <DistroName>
```
