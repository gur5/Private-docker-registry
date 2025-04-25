# Private-docker-registry
## Implementing a Private Docker Registry on Debian/Ubuntu 
A Private Docker Registry allows you to store and manage container images privately instead of using Docker Hub. This is useful for security, performance, and better control over your images in a DevOps workflow.
### Overview

-	**Operating System**: Debian/Ubuntu
-	**Registry Access:** Private (secured with authentication)
-	**Storage Location:** Local or Cloud
-	**Security:** Secured with TLS (SSL certificate)


## Step 1: Install Docker and Dependencies
### 1.1 Update Your System
Before installing Docker, it's best to update your package list and upgrade existing packages:
```
sudo apt update 
```
-	sudo apt update: Updates the list of available packages from repositories.
-	sudo apt upgrade -y: Upgrades all installed packages to their latest versions.

### 1.2 Install Docker and Docker Compose
```
sudo apt install -y docker.io
sudo systemctl enable --now docker

```

-	sudo apt install -y docker.io: Installs Docker.
-	sudo systemctl enable --now docker: Enables Docker to start on boot and starts it immediately.

### 1.3 Verify Docker Installation

```
docker --version
sudo usermod -aG docker $USER
newgrp docker

```
- This command confirms that Docker has been installed correctly.

## Step 2: Run a Local Docker Registry
Docker provides an official registry image that allows you to host your own private registry.
### 2.1 Start the Registry
```
docker run -d -p 5000:5000 --name registry --restart always registry:2
```
-	docker run -d: Runs the container in detached mode (background).
-	-p 5000:5000: Maps port 5000 on the host to port 5000 inside the container.
-	--name registry: Assigns the container the name "registry."
-	--restart always: Ensures the container restarts automatically if it stops.
-	registry:2: Uses the official Docker registry version 2 image.












