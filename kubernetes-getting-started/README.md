# Kubernetes : Getting Started

## Kubernetes - Installation on Ubuntu Ubuntu 18.04 Bionic Beaver Linux


### Prequisites

If you are using Kubernetes 1.8+ and if swap is on, turn it off.
You can check if you have swap enabled by typing in cat /proc/swaps.
If you have a swap file or partition enabled then turn it off with swapoff.

```
sudo swapoff -a
```

You can make this permanent by commenting out the swap file in /etc/fstab.
```
# CLOUD_IMG: This file was created/modified by the Cloud Image build process
UUID=164a7d1b-28b8-429c-b368-eb6cd38bb69b       /        ext4   defaults,discard        0 0
LABEL=UEFI      /boot/efi       vfat    defaults,discard        0 0
#/dev/disk/cloud/azure_resource-part1   /mnt    auto    defaults,nofail,x-systemd.requires=cloud-init.service,comment=cloudconfig       0       2
```

### Installation procedure

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
