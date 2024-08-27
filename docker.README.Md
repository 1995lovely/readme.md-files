

# Install Docker Engine On Linux

## Set up the repository

```bash
 sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
## Install Yum-utils Package

```bash
  yum install yum-utils -y
```
## Install Docker Engine

```bash
sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
## Start Docker Service

```bash
  sudo systemctl start docker
```
## Enable Docker Service

```bash
sudo systemctl enable docker 
```
## Verify that the Docker Engine installation is successful by running the hello-world image.

```bash
sudo docker run hello-world
```
