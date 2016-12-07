* An uber optimization is the possibility to run all tasks of a MapReduce job in the ApplicationMaster's JVM if the job is small enough.
* The Kerberos Security Realm value is displayed under Administration -> Settings -> Kerberos -> Kerberos Security Realm
* Which CDH service(s) host a property for enabling Kerberos authentication?
-- Cloudera Manager
* To upgrade the CM agents, you may use the Upgrade Wizard that is invoked when you connect to the Admin Console or manually install the Cloudera Manager agent packages.
* Give the tsquery statement used to chart Hue's CPU utilization?
-- select cgroup_cpu_system_rate, cpu_user_rate where serviceType = HUE
* Roles that make up the Hive service are Hive Gateway, Hive Metastore Server and the HiveServer2
* What steps must be completed before integrating Cloudera Manager with Kerberos?
-- From https://www.cloudera.com/documentation/enterprise/5-6-x/topics/cm_sg_intro_kerb.html
  1. Install Cloudera Manager and CDH
  2. If You are Using AES-256 Encryption, Install the JCE Policy File
  3. Get or Create a Kerberos Principal for the Cloudera Manager Server
  4. Enabling Kerberos Using the Wizard
  5. Create the HDFS Superuser
  6. Get or Create a Kerberos Principal for Each User Account
  7. Prepare the Cluster for Each User
  8. Verify that Kerberos Security is Working
  9. (Optional) Enable Authentication for HTTP Web Consoles for Hadoop Roles
 
