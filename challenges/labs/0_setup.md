* List the region, AMI ID, and OS you are using
```
Region: Asia Pacific Singapore
ap-southeast-1a
AMI Used: Red Hat Enterprise Linux (RHEL) 6
http://aws.amazon.com/marketplace/seller-profile?ref=cns_srchrow&id=e6a5002c-6dd0-4d1e-8196-0a1d1857229b
AMI ID:
i-003afaa7
i-043afaa3
i-063afaa1
i-073afaa0
i-2c3dfd8b
```
* List the volume space you have available on each node
ec2-user@ip-172-31-15-248
```
[ec2-user@ip-172-31-15-248 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.0G   45G   5% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
```
ec2-user@ip-172-31-2-18
```
[ec2-user@ip-172-31-2-18 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.0G   45G   5% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
```
ec2-user@ip-172-31-2-20
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.0G   45G   5% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
```
ec2-user@ip-172-31-2-21
```
[ec2-user@ip-172-31-2-21 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.0G   45G   5% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
```
ec2-user@ip-172-31-2-22
```
[ec2-user@ip-172-31-2-22 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.0G   45G   5% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
```
* List the command and output for yum repolist enabled
```
[root@ip-172-31-15-248 ~]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, security
rhui-REGION-client-config-server-6                                                                                                                                | 2.9 kB     00:00
rhui-REGION-client-config-server-6/primary_db                                                                                                                     | 5.9 kB     00:00
rhui-REGION-rhel-server-releases                                                                                                                                  | 3.5 kB     00:00
rhui-REGION-rhel-server-releases/primary_db                                                                                                                       |  51 MB     00:00
rhui-REGION-rhel-server-releases-optional                                                                                                                         | 3.5 kB     00:00
rhui-REGION-rhel-server-releases-optional/primary_db                                                                                                              | 5.0 MB     00:00
rhui-REGION-rhel-server-rh-common                                                                                                                                 | 3.8 kB     00:00
rhui-REGION-rhel-server-rh-common/primary_db                                                                                                                      |  65 kB     00:00
repo id                                                                       repo name                                                                                            status
rhui-REGION-client-config-server-6                                            Red Hat Update Infrastructure 2.0 Client Configuration Server 6                                           6
rhui-REGION-rhel-server-releases                                              Red Hat Enterprise Linux Server 6 (RPMs)                                                             18,378
rhui-REGION-rhel-server-releases-optional                                     Red Hat Enterprise Linux Server 6 Optional (RPMs)                                                    10,444
rhui-REGION-rhel-server-rh-common                                             Red Hat Enterprise Linux Server 6 RH Common (RPMs)                                                      129
repolist: 28,957
```
```
[root@ip-172-31-2-18 ~]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, security
rhui-REGION-client-config-server-6                                                                                                                                | 2.9 kB     00:00
rhui-REGION-client-config-server-6/primary_db                                                                                                                     | 5.9 kB     00:00
rhui-REGION-rhel-server-releases                                                                                                                                  | 3.5 kB     00:00
rhui-REGION-rhel-server-releases/primary_db                                                                                                                       |  51 MB     00:00
rhui-REGION-rhel-server-releases-optional                                                                                                                         | 3.5 kB     00:00
rhui-REGION-rhel-server-releases-optional/primary_db                                                                                                              | 5.0 MB     00:00
rhui-REGION-rhel-server-rh-common                                                                                                                                 | 3.8 kB     00:00
rhui-REGION-rhel-server-rh-common/primary_db                                                                                                                      |  65 kB     00:00
repo id                                                                       repo name                                                                                            status
rhui-REGION-client-config-server-6                                            Red Hat Update Infrastructure 2.0 Client Configuration Server 6                                           6
rhui-REGION-rhel-server-releases                                              Red Hat Enterprise Linux Server 6 (RPMs)                                                             18,378
rhui-REGION-rhel-server-releases-optional                                     Red Hat Enterprise Linux Server 6 Optional (RPMs)                                                    10,444
rhui-REGION-rhel-server-rh-common                                             Red Hat Enterprise Linux Server 6 RH Common (RPMs)                                                      129
repolist: 28,957
```
```
[root@ip-172-31-2-20 ~]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, security
rhui-REGION-client-config-server-6                                                                                                                                | 2.9 kB     00:00
rhui-REGION-client-config-server-6/primary_db                                                                                                                     | 5.9 kB     00:00
rhui-REGION-rhel-server-releases                                                                                                                                  | 3.5 kB     00:00
rhui-REGION-rhel-server-releases/primary_db                                                                                                                       |  51 MB     00:00
rhui-REGION-rhel-server-releases-optional                                                                                                                         | 3.5 kB     00:00
rhui-REGION-rhel-server-releases-optional/primary_db                                                                                                              | 5.0 MB     00:00
rhui-REGION-rhel-server-rh-common                                                                                                                                 | 3.8 kB     00:00
rhui-REGION-rhel-server-rh-common/primary_db                                                                                                                      |  65 kB     00:00
repo id                                                                       repo name                                                                                            status
rhui-REGION-client-config-server-6                                            Red Hat Update Infrastructure 2.0 Client Configuration Server 6                                           6
rhui-REGION-rhel-server-releases                                              Red Hat Enterprise Linux Server 6 (RPMs)                                                             18,378
rhui-REGION-rhel-server-releases-optional                                     Red Hat Enterprise Linux Server 6 Optional (RPMs)                                                    10,444
rhui-REGION-rhel-server-rh-common                                             Red Hat Enterprise Linux Server 6 RH Common (RPMs)                                                      129
repolist: 28,957
```
```
[root@ip-172-31-2-21 ~]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, security
repo id                                                                       repo name                                                                                            status
rhui-REGION-client-config-server-6                                            Red Hat Update Infrastructure 2.0 Client Configuration Server 6                                           6
rhui-REGION-rhel-server-releases                                              Red Hat Enterprise Linux Server 6 (RPMs)                                                             18,378
rhui-REGION-rhel-server-releases-optional                                     Red Hat Enterprise Linux Server 6 Optional (RPMs)                                                    10,444
rhui-REGION-rhel-server-rh-common                                             Red Hat Enterprise Linux Server 6 RH Common (RPMs)                                                      129
repolist: 28,957
```
[root@ip-172-31-2-22 ~]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, security
rhui-REGION-client-config-server-6                                                                                                                                | 2.9 kB     00:00
rhui-REGION-client-config-server-6/primary_db                                                                                                                     | 5.9 kB     00:00
rhui-REGION-rhel-server-releases                                                                                                                                  | 3.5 kB     00:00
rhui-REGION-rhel-server-releases/primary_db                                                                                                                       |  51 MB     00:00
rhui-REGION-rhel-server-releases-optional                                                                                                                         | 3.5 kB     00:00
rhui-REGION-rhel-server-releases-optional/primary_db                                                                                                              | 5.0 MB     00:00
rhui-REGION-rhel-server-rh-common                                                                                                                                 | 3.8 kB     00:00
rhui-REGION-rhel-server-rh-common/primary_db                                                                                                                      |  65 kB     00:00
repo id                                                                       repo name                                                                                            status
rhui-REGION-client-config-server-6                                            Red Hat Update Infrastructure 2.0 Client Configuration Server 6                                           6
rhui-REGION-rhel-server-releases                                              Red Hat Enterprise Linux Server 6 (RPMs)                                                             18,378
rhui-REGION-rhel-server-releases-optional                                     Red Hat Enterprise Linux Server 6 Optional (RPMs)                                                    10,444
rhui-REGION-rhel-server-rh-common                                             Red Hat Enterprise Linux Server 6 RH Common (RPMs)                                                      129
repolist: 28,957
```
