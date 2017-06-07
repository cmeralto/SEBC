1 - What is ubertask optimization?
- An Uber task means that the ApplicationMaster uses its own JVM to run Map and Reduce tasks, so the tasks are executed sequentially on one node. In this case YARN has to allocate a container for ApplicationMaster only. Whether to enable the small-jobs "ubertask" optimization, which runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the following maxmaps, maxreduces, and maxbytes settings. 

2 - Where in CM is the Kerberos Security Realm value displayed?
- In CM go to Administration -> Settings -> Kerberos -> Find "Kerberos Security Realm" parameter value

3 - Which CDH service(s) host a property for enabling Kerberos authentication?
- HDFS, MapReduce, YARN, Accumulo, Flume, HBase, Hive, Hue, Impala, Oozie, Pig, Search, Sentry, Spark, Sqoop, Sqoop2, Zookeeper.
- Resource: https://www.cloudera.com/documentation/enterprise/5-8-x/topics/sg_auth_overview.html

4 - How do you upgrade the CM agents?
-

5 - Give the tsquery statement used to chart Hue's CPU utilization?
-

6 - Name all the roles that make up the Hive service
-

7 - What steps must be completed before integrating Cloudera Manager with Kerberos?
-