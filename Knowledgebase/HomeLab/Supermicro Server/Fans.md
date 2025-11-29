
using ipmitool

![[Pasted image 20230331110236.png]]

To set the lower thresholds, use:
`~# ipmitool sensor thresh "*sensor name*" lower *lnr* *lcr* *lnc*`

  
To set the upper thresholds, use:  
`~# ipmitool sensor thresh "*sensor name*" upper *unc* *ucr* *unr*`

Finally reset the BMC:
$ ipmitool -I lanplus -H 192.168.1.112 -U ADMIN -P ADMIN mc reset cold

![[Pasted image 20230331111328.png]]