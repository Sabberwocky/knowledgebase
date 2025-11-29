
“When the NoMachine (server) computer is behind a NAT router or a firewall, NoMachine tries to use the UPnP or NAT-PMP protocol (depending on what is supported by the router) to:

– Retrieve the public or external IP of the host machine where it’s installed.

– Configure the router to allow a NoMachine client to connect from outside of the private network.”  
First I would suggest to check if:

– your router has enabled UPnP or NAT-PMP protocol, if not try to enable it and then restart the router.

– Please check that UPnP is enabled on nxserver.

Check the key ‘EnableUPnP’ in server.cfg if it is set to NX, if not set it and restart nxserver.  
Then please run a terminal and execute the commands:

```
sudo /etc/NX/nxserver --upnpmap
sudo /etc/NX/nxserver --upnpstatus
```

If the router doesn’t support UPnP or NAT-PMP protocol or you still don’t see the ports you will have to configure port forwarding by using the router admin interface. This is normally a Web application running at [http://192.168.1.1](http://192.168.1.1). Follow these instructions for your router:

1. Reserve local IP of your computer on router according to your router’s instructions.  
2. Open a unique port for that local IP in Port Forwarding section on the router.  
3. Check public IP of the router.  
4. Now in your Player connection settings – enter the public IP of your router and unique port. Now you should connect to your machine.