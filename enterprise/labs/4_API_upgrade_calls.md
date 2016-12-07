* Get latest API version
```
[ec2-user@ip-172-31-3-11 yum.repos.d]$ curl -X GET -u admin:admin 'http://54.254.163.92:7180/api/version'
v14
```
* Report the CM version
```
[ec2-user@ip-172-31-3-11 yum.repos.d]$ curl -X GET -u admin:admin 'http://54.254.163.92:7180/api/v14/cm/version'
{
  "version" : "5.9.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20161006-1801",
  "gitHash" : "898a5e032c080e18833dfc58180761f6ef2ea351",
  "snapshot" : false
}
```
* List all CM users
```
[ec2-user@ip-172-31-3-11 yum.repos.d]$ curl -X GET -u admin:admin 'http://54.254.163.92:7180/api/v14/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_CLUSTER_ADMIN" ]
  } ]
}[
[ec2-user@ip-172-31-3-11 yum.repos.d]$ curl -X GET -u robgajudo:cloudera 'http://54.254.163.92:7180/api/v14/users'
{
  "items" : [ {
    "name" : "robgajudo",
    "roles" : [ "ROLE_USER_ADMIN" ]
  } ]
}
```

* Report the database server in use by CM
```
[ec2-user@ip-172-31-3-11 yum.repos.d]$ curl -X GET -u admin:admin 'http://54.254.163.92:7180/api/v14/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}[
```
