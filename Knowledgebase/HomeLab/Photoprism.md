


SMB mount to photoimport
---

mounting script at /mnt/mount-smb-share.sh
service at /etc/systemd/system/mount-smb-share.service

Create a new script file, for example: `/usr/local/bin/mount-smb-share.sh`  
Add the following content to the script file:

```bash
#/bin/bash sleep 30 # Wait for 30 seconds to ensure that the network is fully available
mount -t cifs //10.117.117.103/DataPool/exchange/photoimport /mnt/DataPoolNVME/photoprism/photoimport -o username=hubadu,password=juhu,uid=1000,gid=1000,iocharset=utf8,file_mode=0777,dir_mode=0777,noperm
```    
Note: You may need to adjust the `sleep` duration to a longer or shorter period depending on your network setup.
    
Make the script file executable by running the command:
```bash
chmod +x /usr/local/bin/mount-smb-share.sh
```
Create a new systemd service file for the mount script, for example: 
```bash
/etc/systemd/system/mount-smb-share.service`
```
   
Add the following content to the service file:
   
 makefile

[Unit] 
Description=Mount SMB share 
After=network-online.target 
Wants=network-online.target  

[Service] 
Type=oneshot 
ExecStart=/usr/local/bin/mount-smb-share.sh  

[Install] 
WantedBy=multi-user.target`

This service file ensures that the mount script is executed after the network is fully available.

Reload the systemd daemon to read the new service file:

```bash
systemctl daemon-reload`
```
 Enable the service to start at boot time:

```bash
systemctl enable mount-smb-share.service
```

With this setup, the `mount-smb-share.sh` script will be executed 30 seconds after the system has fully booted, and the SMB share should be mounted successfully.