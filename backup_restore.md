## Reference 
https://pve.proxmox.com/wiki/Backup_and_Restore

## Backup 
Backups are done via the GUI 

## Restore
### VM
VMs are restored using the CLI utility `qmrestore`

#### Restore example
```sh
# qmrestore <vm image> <vmid>
qmrestore vzdump-qemu-301-2024_12_14-15_25_01.vma.zst 301
```

### Containers
Containers are restored using the CLI utility `pct restore`

## Backup Location
### 1. Local
If you're saving backups to local storage, they'll be at `/var/lib/vz/dump/`
