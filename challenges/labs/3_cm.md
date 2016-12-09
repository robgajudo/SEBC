```
[root@ip-172-31-15-248 ~]# sudo -u hdfs hdfs dfs -ls /user
Found 6 items
drwxrwxrwx   - mapred hadoop              0 2016-12-08 22:14 /user/history
drwxrwxr-t   - hive   hive                0 2016-12-08 22:14 /user/hive
drwxrwxr-x   - hue    hue                 0 2016-12-08 22:15 /user/hue
drwxrwxr-x   - oozie  oozie               0 2016-12-08 22:15 /user/oozie
drwxr-xr-x   - hdfs   supergroup          0 2016-12-08 22:19 /user/orchard
drwxr-xr-x   - hdfs   supergroup          0 2016-12-08 22:19 /user/raffles
```
```
[root@ip-172-31-15-248 ~]# curl -X GET -u admin:admin 'http://ec2-54-254-135-60.ap-southeast-1.compute.amazonaws.com:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "i-2c3dfd8b",
    "ipAddress" : "172.31.15.248",
    "hostname" : "ip-172-31-15-248.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-15-248.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/i-2c3dfd8b",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15605030912
  }, {
    "hostId" : "i-003afaa7",
    "ipAddress" : "172.31.2.18",
    "hostname" : "ip-172-31-2-18.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-15-248.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/i-003afaa7",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15605030912
  }, {
    "hostId" : "i-063afaa1",
    "ipAddress" : "172.31.2.20",
    "hostname" : "ip-172-31-2-20.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-15-248.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/i-063afaa1",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15605030912
  }, {
    "hostId" : "i-073afaa0",
    "ipAddress" : "172.31.2.21",
    "hostname" : "ip-172-31-2-21.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-15-248.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/i-073afaa0",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15605030912
  }, {
    "hostId" : "i-043afaa3",
    "ipAddress" : "172.31.2.22",
    "hostname" : "ip-172-31-2-22.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-15-248.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/i-043afaa3",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15605030912
  } ]
}
```
