# Prequisites

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
