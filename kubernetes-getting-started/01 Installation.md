# Installation procedure - on Ubuntu 18.04 Bionic Beaver Linux

Update apt package index
```
sudo apt-get update
```
Install apt-transport-https, ca-certificates, curl and software-properties-common
packages.
```  
sudo apt-get --yes install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```
Import docker PGP key
```
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
Register Docker repository
```
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```
Update apt package index
```
sudo apt-get update
```
Import Kubernetes PGP key
```
sudo su
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
```
Register Kubernetes repository
```
sudo su
cat <<EOF >/etc/apt/sources.list.d/kubernetes.list
deb http://apt.kubernetes.io/ kubernetes-xenial main
EOF
```
Update apt package index and install docker.io, kubeadm, kubectl, kubelet, kubernetes-cni
components
```
sudo apt-get update
sudo apt-get install -y docker.io kubeadm kubectl kubelet kubernetes-cni
```
