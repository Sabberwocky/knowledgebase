
setup: https://youtu.be/NKc3k7xceT8
troubleshoot: https://youtu.be/C0nxOZBo6Dw

ssh
152.67.70.98
152.64.78.0
ubunbu
Hck7_4oracle

```bash
sudo apt-get udpate
sudo apt-get udgrade
sudo apt-get install ubuntu-desktop
sudo apt-get install xrdp    (demote desptop)
sudo apt-get install stacer     (hardware monitoring)
sudo cp /etc/iptables/rules.v4 /etciptables/rules.v4.bak && sudo trunctate -s 0 /etc/iptables/rules.v4   (this backups the internal firewall in rules.v4 and more or less wipes it, so that no internal firewall is present (lowers complexity))
sudo rm /usr/share/polkit-1/actions/org.freedesktop.color.policy (removes 5min reminder policy to password authorizations for a colored device )
sudo passwd ubuntu
sudo reboot

```

troubleshoot
```bash
systemctl status xrdp
```

this indicates, xrdp is only listening on ipv6 address and not ipv4
```bash
ubuntu@ubuntu-2204:~$ ubuntu@ubuntu-2204:~$ sudo netstat -nat | grep 3389
tcp6       0      0 :::3389                 :::*                    LISTEN
```

```bash
sudo nano /etc/xrdp/xrdp.ini
```

change
```bash
port=3389 => port=tcp://:3389
```

restart xrdp
```bash
sudo service xrdp restart
```

result should looks like
```bash
ubuntu@ubuntu-2204:~$ sudo netstat -nat | grep 3389
tcp        0      0 0.0.0.0:3389            0.0.0.0:*               LISTEN
```

indicates that port is open:
```
ubuntu@ubuntu-2204:~$ telnet localhost 3389
Trying 127.0.0.1...
Connected to localhost.
```

