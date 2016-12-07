Curl commands for Hive
* Check Hive Status
```
[ec2-user@ip-172-31-3-11 ~]$ curl -u admin:admin 'http://54.254.163.92:7180/api/v2/clusters/RobGajudo/services/hive/'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-3-11.ap-southeast-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
```
* Stop Hive Service
```
[ec2-user@ip-172-31-3-11 ~]$ curl -X POST -u admin:admin 'http://54.254.163.92:7180/api/v2/clusters/RobGajudo/services/hive/commands/stop'
{
  "id" : 490,
  "name" : "Stop",
  "startTime" : "2016-12-07T04:01:41.014Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```
  * Hive Service Stopping
```
[ec2-user@ip-172-31-3-11 ~]$ curl u admin:admin 'http://54.254.163.92:7180/api/v2/clusters/RobGajudo/services/hive/''
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-3-11.ap-southeast-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STOPPING",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}
```
  * Hive Service Already Stopped
```
[ec2-user@ip-172-31-3-11 ~]$curl -u admin:admin 'http://54.254.163.92:7180/api/v2/clusters/RobGajudo/services/hive/'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-3-11.ap-southeast-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STOPPED",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}
```
* Starting Hive Services
```
[ec2-user@ip-172-31-3-11 ~]$ curl -X POST -u admin:admin 'http://54.254.163.92:7180/api/v2/clusters/RobGajudo/services/hive/commands/start'
{
  "id" : 494,
  "name" : "Start",
  "startTime" : "2016-12-07T04:06:26.702Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```
  * Hive Services Started
```
[ec2-user@ip-172-31-3-11 ~]$ curl u admin:admin 'http://54.254.163.92:7180/api/v2/clusters/RobGajudo/services/hive/''
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-3-11.ap-southeast-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}
```
