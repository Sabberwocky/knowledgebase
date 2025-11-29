ubuntu@oracleubuntu-2204-v2:~$ sudo chmod 600 /mnt/1GiB.swap
ubuntu@oracleubuntu-2204-v2:~$ sudo mkswap /mnt/1GiB.swap
Setting up swapspace version 1, size = 1024 MiB (1073737728 bytes)
no label, UUID=1b4b6099-6cd9-4f8e-946d-5132390cb12c
ubuntu@oracleubuntu-2204-v2:~$ sudo swapon /mnt/1GiB.swap
ubuntu@oracleubuntu-2204-v2:~$ cat /proc/swaps
Filename                                Type            Size            Used            Priority
/mnt/1GiB.swap                          file            1048572         0               -2
ubuntu@oracleubuntu-2204-v2:~$ echo '/mnt/1GiB.swap swap swap defaults 0 0' | sudo tee -a /etc/fstab
/mnt/1GiB.swap swap swap defaults 0 0
ubuntu@oracleubuntu-2204-v2:~$




## Kasm


```bash
Installation Complete


Kasm UI Login Credentials

------------------------------------
  username: admin@kasm.local
  password: vSdFjnpZISqVX
------------------------------------
  username: user@kasm.local
  password: INt9SHbpPUsjy
------------------------------------

Kasm Database Credentials
------------------------------------
  username: kasmapp
  password: p8dxmDhthQGTOqIjvW40
------------------------------------

Kasm Redis Credentials
------------------------------------
  password: qsYkJzLc8m83hN4MyBpd
------------------------------------

Kasm Manager Token
------------------------------------
  password: zP8kFfuTfQHs2fR2uawx
------------------------------------

Kasm Guac Token
------------------------------------
  password: bZoudpDi7sfNnLGSsyP5GW
------------------------------------

Service Registration Token
------------------------------------
  password: jAeXTE4wOiavkh0eWxUv
------------------------------------
```

