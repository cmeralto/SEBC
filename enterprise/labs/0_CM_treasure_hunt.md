1 - What is ubertask optimization?
- An Uber task means that the ApplicationMaster uses its own JVM to run Map and Reduce tasks, so the tasks are executed sequentially on one node. In this case YARN has to allocate a container for ApplicationMaster only. Whether to enable the small-jobs "ubertask" optimization, which runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the following maxmaps, maxreduces, and maxbytes settings. 

2 - Where in CM is the Kerberos Security Realm value displayed?
- In CM go to Administration -> Settings -> Kerberos -> Find "Kerberos Security Realm" parameter value

3 - Which CDH service(s) host a property for enabling Kerberos authentication?
- HDFS, MapReduce, YARN, Accumulo, Flume, HBase, Hive, Hue, Impala, Oozie, Pig, Search, Sentry, Spark, Sqoop, Sqoop2, Zookeeper.
- Resource: https://www.cloudera.com/documentation/enterprise/5-8-x/topics/sg_auth_overview.html

4 - How do you upgrade the CM agents?
```
1- Start by stopping the services
2- Upgrade the repos if necessary
3- Update the packages for the cloudera-scm-server, cloudera-scm-daemons and cloudera-scm-agent
4- Restart the server
5- Log in to the Cloudera Manager Admin Console. The Upgrade Wizard displays
6- Upgrade the Agent software using Cloudera Manager
Resource: https://www.cloudera.com/documentation/enterprise/5-8-x/topics/cm_ag_ug_cm5.html#concept_gs4_bsg_xw
```

5 - Give the tsquery statement used to chart Hue's CPU utilization?
- select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME
- $SERVICENAME = hue  $CLUSTERID = 1
- select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=hue

6 - Name all the roles that make up the Hive service
- Gateway, Hive Metastore Server, HiveServer2

7 - What steps must be completed before integrating Cloudera Manager with Kerberos?
- Set up a working KDC. Cloudera Manager supports authentication with MIT KDC and Active Directory.
- Configure the KDC to allow renewable tickets with non-zero ticket lifetimes. 
- openldap-clients on the Cloudera Manager Server host
- krb5-workstation, krb5-libs on ALL hosts
- Create an account for Cloudera Manager that has the permissions to create other accounts in the KDC
