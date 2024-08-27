

# Install Kubernetes On Red Hat-based distributions

## Set up the repository

```bash
 cat <<EOF | sudo tee /etc/yum.repos.d/kubernetes.repo
[kubernetes]
name=Kubernetes
baseurl=https://pkgs.k8s.io/core:/stable:/v1.31/rpm/
enabled=1
gpgcheck=1
gpgkey=https://pkgs.k8s.io/core:/stable:/v1.31/rpm/repodata/repomd.xml.key
EOF
```
## Install kubectl

```bash
  sudo yum install -y kubectl
```
## Install Kubeadm

```bash
sudo yum install Kubeadm -y
```
## Install Kubelet

```bash
  sudo install kubelet -y
  ```
## Start Kubelet Service

```bash
sudo systemctl start kubelet 
```
## Enable Kubelet Service

```bash
sudo systemctl enable kubelet 
```
