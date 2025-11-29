User: root
PW: HorizonLab_PVE


## ZFS Pool 2x2TB

root@pve:~# zpool create backupSynPool nvme0n1p1 nvme1n1p1
root@pve:~# df -H
Filesystem        Size  Used Avail Use% Mounted on
udev               34G     0   34G   0% /dev
tmpfs             6.8G  9.1M  6.8G   1% /run
rpool/ROOT/pve-1  403G   20G  383G   5% /
tmpfs              34G   48M   34G   1% /dev/shm
tmpfs             5.3M     0  5.3M   0% /run/lock
rpool             383G  132k  383G   1% /rpool
rpool/data        383G  132k  383G   1% /rpool/data
rpool/ROOT        383G  132k  383G   1% /rpool/ROOT
/dev/fuse         135M   21k  135M   1% /etc/pve
tmpfs             6.8G     0  6.8G   0% /run/user/0
backupSynPool     3.9T  132k  3.9T   1% /backupSynPool
root@pve:~# 

list all hardware disks
```bash 
lsblk 
```

list mounted disks
```bash
df -H
```

create ZFS pool of multiple disks
```bash
zpool create backupSynPool nvme0n1p1 nvme1n1p1
```

![[Pasted image 20230315202555.png]]

https://forum.proxmox.com/threads/raid0-or-striped-disks.65507/
![[Pasted image 20230315202937.png]]

add as storage
![[Pasted image 20230315212042.png]]



## mount disk

best source: https://phoenixnap.com/kb/linux-create-partition

```bash

mkdir backupSynology
sudo mount -t ext4 /dev/sdb backupSynology

```
