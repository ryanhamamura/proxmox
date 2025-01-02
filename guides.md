
## Proxmox Lost Quorum
```sh
# Stop pve-cluster
systemctl stop pve-cluster

# Stop corosync
systemctl stop corosync

# Force local mode
pmxcfs -l

# Clean up old cluster 
rm /etc/pve/corosync.conf
rm /etc/corosync/*

# Reboot
reboot
```
