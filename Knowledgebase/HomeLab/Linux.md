MaTTh1as_parsec
## SSH

```bash 
ssh username@server_IP
```

---

## RSYNC

```bach
rsync [OPTIONEN] QUELLE(N) ZIEL
rsync -a source target
rsync -avz -e ssh user@source_vm:/var/www/ user@target_vm:/path/to/backup/
hubadu@hubadu-virtual-machine:/$ sudo rsync -avz -e ssh /var/www/ hubadu@10.117.117.201:/var/www/

```

SCP
---

```bash
scp /path/to/file user@server:/path/to/destination
```


UNZIP
---

```bash
unzip filename.zip -d /path/to/directory
```