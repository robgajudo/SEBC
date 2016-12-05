System Configuration Checks

- Check vm.swappiness

Steps in setting vm.swappiness to 1

```
[ec2-user@ip-172-31-3-11 ~]$ sudo vi /etc/sysctl.conf
#VM Swappiness
vm.swappiness=1
```
Make it persistent
```
sudo sysctl -p
```
Show current vm.swappiness value
```
[ec2-user@ip-172-31-3-11 ~]$ cat /proc/sys/vm/swappiness
1
```
- Show the mount attributes of all volumes
```
[ec2-user@ip-172-31-3-11 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       32G  2.0G   28G   7% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
```
- Show the reserve space of any non-root, ext-based volumes

None as of the moment

- Show that transparent hugepages is disabled
```
[ec2-user@ip-172-31-3-11 ~]$ cat /proc/sys/vm/nr_hugepages
0
[ec2-user@ip-172-31-3-11 ~]$ grep -i HugePages_Total /proc/meminfo
HugePages_Total:       0
```
- Report the network interface attributes
```
[ec2-user@ip-172-31-3-11 ~]$ ifconfig
eth0      Link encap:Ethernet  HWaddr 02:47:E7:25:B4:6D
          inet addr:172.31.3.11  Bcast:172.31.15.255  Mask:255.255.240.0
          inet6 addr: fe80::47:e7ff:fe25:b46d/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1
          RX packets:2419 errors:0 dropped:0 overruns:0 frame:0
          TX packets:1938 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:191078 (186.5 KiB)  TX bytes:196643 (192.0 KiB)
          Interrupt:24

lo        Link encap:Local Loopback
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:16436  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:0 (0.0 b)  TX bytes:0 (0.0 b)
```
- Show forward and reverse host lookups using getent and nslookup

getent
```
[ec2-user@ip-172-31-3-11 ~]$ getent ahostsv4 ip-172-31-3-11
172.31.3.11     STREAM ip-172-31-3-11.ap-southeast-1.compute.internal
172.31.3.11     DGRAM
172.31.3.11     RAW
```
nslookup
```
[ec2-user@ip-172-31-3-11 ~]$ nslookup ip-172-31-3-11
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-3-11.ap-southeast-1.compute.internal
Address: 172.31.3.11
```
- Verify the nscd service is running

nscd is not installed by default, install nscd using yum
```
[ec2-user@ip-172-31-3-11 ~]$ sudo yum install nscd
```
Start nscd service and make it persistent.
```
[ec2-user@ip-172-31-3-11 ~]$ sudo service nscd start
Starting nscd:                                             [  OK  ]
[ec2-user@ip-172-31-3-11 ~]$ sudo chkconfig nscd on
```
Check nscd status
```
[ec2-user@ip-172-31-3-11 ~]$ sudo service nscd status
nscd (pid 2329) is running...
```

- Verify the ntpd service is running
Start ntpd service and make it persistent.
```
[ec2-user@ip-172-31-3-11 ~]$ sudo service ntpd start
Starting ntpd:                                             [  OK  ]
[ec2-user@ip-172-31-3-11 ~]$ sudo chkconfig ntpd on
```
Verify ntpd status
```
[ec2-user@ip-172-31-3-11 ~]$ sudo service ntpd status
ntpd (pid  2407) is running...
[ec2-user@ip-172-31-3-11 ~]$ ntpq -p
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
 fnet70-f101-acc .STEP.          16 u   26   64    0    0.000    0.000   0.000
+netmon2.dcs1.bi 179.43.76.147    2 u   11   64    1   53.814   -2.046   1.384
+210.23.18.200   .PPS.            1 u   10   64    1   51.855   -1.989   1.972
*time3.maxonline .GPS.            1 u    8   64    1    2.188   21.408   0.031
```
