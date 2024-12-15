## Reference 
https://pve.proxmox.com/wiki/Backup_and_Restore

## Backup 
Backups are done via the GUI 

## Restore
VMs are restored using the CLI utility `qmrestore`
Containers are restored using the CLI utility `pct restore`

## Backup Location
### 1. Local
If you're saving backups to local storage, they'll be at `/var/lib/vz/dump/`