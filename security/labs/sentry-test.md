- Verify user privileges
```
[root@ip-172-31-32-24 ~]# sudo su - cmeralto
[cmeralto@ip-172-31-32-24 ~]$ kinit
Password for cmeralto@CMERALTO.COM:
```

```
[cmeralto@ip-172-31-32-24 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_500
Default principal: cmeralto@CMERALTO.COM

Valid starting     Expires            Service principal
06/07/17 22:52:29  06/08/17 22:52:29  krbtgt/CMERALTO.COM@CMERALTO.COM
        renew until 06/14/17 22:52:29
```

```
[cmeralto@ip-172-31-32-24 ~]$ beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM
scan complete in 3ms
Connecting to jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM
Enter username for jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM: cmeralto
Enter password for jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> show tables;
INFO  : Compiling command(queryId=hive_20170607225353_e98c11ac-0e80-41d8-83c6-83c348a92f88): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170607225353_e98c11ac-0e80-41d8-83c6-83c348a92f88); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20170607225353_e98c11ac-0e80-41d8-83c6-83c348a92f88): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170607225353_e98c11ac-0e80-41d8-83c6-83c348a92f88); Time taken: 0.15 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.35 seconds)
```

- Create a Sentry role with full authorization
```
beeline> !connect jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM
scan complete in 3ms
Connecting to jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM
Enter username for jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM: cmeralto
Enter password for jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170608081616_8f649fb0-fd61-4be0-b6dd-3b6c5c570591): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608081616_8f649fb0-fd61-4be0-b6dd-3b6c5c570591); Time taken: 0.566 seconds
INFO  : Executing command(queryId=hive_20170608081616_8f649fb0-fd61-4be0-b6dd-3b6c5c570591): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608081616_8f649fb0-fd61-4be0-b6dd-3b6c5c570591); Time taken: 0.886 seconds
INFO  : OK
No rows affected (2.628 seconds)
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170608081919_fb6d8332-dd88-4f0d-8968-579c2f0b20ae): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608081919_fb6d8332-dd88-4f0d-8968-579c2f0b20ae); Time taken: 0.093 seconds
INFO  : Executing command(queryId=hive_20170608081919_fb6d8332-dd88-4f0d-8968-579c2f0b20ae): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608081919_fb6d8332-dd88-4f0d-8968-579c2f0b20ae); Time taken: 0.093 seconds
INFO  : OK
No rows affected (0.198 seconds)
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> GRANT ROLE sentry_admin TO GROUP cmeralto;
INFO  : Compiling command(queryId=hive_20170608081919_45caafb7-d154-4588-ad84-b73a969a8100): GRANT ROLE sentry_admin TO GROUP cmeralto
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608081919_45caafb7-d154-4588-ad84-b73a969a8100); Time taken: 0.081 seconds
INFO  : Executing command(queryId=hive_20170608081919_45caafb7-d154-4588-ad84-b73a969a8100): GRANT ROLE sentry_admin TO GROUP cmeralto
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608081919_45caafb7-d154-4588-ad84-b73a969a8100); Time taken: 0.08 seconds
INFO  : OK
No rows affected (0.171 seconds)
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170608081919_4f387600-3ae1-49dd-9f17-72e16dcf6ba7): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608081919_4f387600-3ae1-49dd-9f17-72e16dcf6ba7); Time taken: 0.287 seconds
INFO  : Executing command(queryId=hive_20170608081919_4f387600-3ae1-49dd-9f17-72e16dcf6ba7): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608081919_4f387600-3ae1-49dd-9f17-72e16dcf6ba7); Time taken: 0.199 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.595 seconds)
```

- Create additional test users
```
sudo groupadd selector
sudo groupadd inserters
sudo useradd -u 1100 -g selector george
sudo useradd -u 1200 -g inserters ferdinand

# kadmin.local
kadmin.local: addprinc george@CMERALTO.COM
kadmin.local: addprinc ferdinand@CMERALTO.COM
kadmin.local:  exit
```

- Create test roles
```
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20170608082929_ffd18f5f-7b52-486f-8902-1c1fcad990cf): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608082929_ffd18f5f-7b52-486f-8902-1c1fcad990cf); Time taken: 0.07 seconds
INFO  : Executing command(queryId=hive_20170608082929_ffd18f5f-7b52-486f-8902-1c1fcad990cf): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608082929_ffd18f5f-7b52-486f-8902-1c1fcad990cf); Time taken: 0.051 seconds
INFO  : OK
No rows affected (0.183 seconds)
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20170608082929_d79779fe-9257-4400-9447-0bb3deef2edd): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608082929_d79779fe-9257-4400-9447-0bb3deef2edd); Time taken: 0.095 seconds
INFO  : Executing command(queryId=hive_20170608082929_d79779fe-9257-4400-9447-0bb3deef2edd): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608082929_d79779fe-9257-4400-9447-0bb3deef2edd); Time taken: 0.028 seconds
INFO  : OK
No rows affected (0.133 seconds)
```

- Grant read privilege for all tables to reads
```
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20170608083030_d83648cf-3ead-4394-8482-a1ae14a37c35): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083030_d83648cf-3ead-4394-8482-a1ae14a37c35); Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20170608083030_d83648cf-3ead-4394-8482-a1ae14a37c35): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083030_d83648cf-3ead-4394-8482-a1ae14a37c35); Time taken: 0.096 seconds
INFO  : OK
No rows affected (0.173 seconds)
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20170608083030_35930f31-e924-4ec3-b7dd-5da91129172b): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083030_35930f31-e924-4ec3-b7dd-5da91129172b); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20170608083030_35930f31-e924-4ec3-b7dd-5da91129172b): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083030_35930f31-e924-4ec3-b7dd-5da91129172b); Time taken: 0.03 seconds
INFO  : OK
No rows affected (0.098 seconds)
```

- Grant read privilege for default.sample07 only to 'writes'
```
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20170608083232_762a1060-b93e-4709-b67d-5f96146b6a01): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083232_762a1060-b93e-4709-b67d-5f96146b6a01); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20170608083232_762a1060-b93e-4709-b67d-5f96146b6a01): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083232_762a1060-b93e-4709-b67d-5f96146b6a01); Time taken: 0.106 seconds
INFO  : OK
No rows affected (0.171 seconds)
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20170608083333_de6f0f13-9816-4691-9130-7ef4a195b259): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083333_de6f0f13-9816-4691-9130-7ef4a195b259); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20170608083333_de6f0f13-9816-4691-9130-7ef4a195b259): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083333_de6f0f13-9816-4691-9130-7ef4a195b259); Time taken: 0.056 seconds
INFO  : OK
No rows affected (0.135 seconds)
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20170608083333_96105a63-4caf-424a-948f-b836a16c3c22): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083333_96105a63-4caf-424a-948f-b836a16c3c22); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20170608083333_96105a63-4caf-424a-948f-b836a16c3c22): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083333_96105a63-4caf-424a-948f-b836a16c3c22); Time taken: 0.035 seconds
INFO  : OK
No rows affected (0.101 seconds)
```

- kinit as george
```
[root@ip-172-31-47-3 ~]# kinit george@CMERALTO.COM
Password for george@CMERALTO.COM:
[root@ip-172-31-47-3 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: george@CMERALTO.COM

Valid starting     Expires            Service principal
06/08/17 08:34:36  06/09/17 08:34:36  krbtgt/CMERALTO.COM@CMERALTO.COM
        renew until 06/15/17 08:34:36
[root@ip-172-31-47-3 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM
scan complete in 4ms
Connecting to jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM
Enter username for jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM: george
Enter password for jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170608083535_e77caf36-b5d1-4fe9-a0af-30fbc30158ac): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083535_e77caf36-b5d1-4fe9-a0af-30fbc30158ac); Time taken: 0.091 seconds
INFO  : Executing command(queryId=hive_20170608083535_e77caf36-b5d1-4fe9-a0af-30fbc30158ac): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083535_e77caf36-b5d1-4fe9-a0af-30fbc30158ac); Time taken: 0.138 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.367 seconds)
```

- ## kinit as ferdinand
```
[root@ip-172-31-47-3 ~]# kinit ferdinand@CMERALTO.COM
Password for ferdinand@CMERALTO.COM:
[root@ip-172-31-47-3 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: ferdinand@CMERALTO.COM

Valid starting     Expires            Service principal
06/08/17 08:35:50  06/09/17 08:35:50  krbtgt/CMERALTO.COM@CMERALTO.COM
        renew until 06/15/17 08:35:50
[root@ip-172-31-47-3 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM
scan complete in 3ms
Connecting to jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM
Enter username for jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM: ferdinand
Enter password for jdbc:hive2://ip-172-31-47-3.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-47-3.eu-west-1.compute.internal@CMERALTO.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-47-3.eu-west-1.comp> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170608083636_ce2693da-bc15-4253-ac5d-d3d44e68eb3e): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608083636_ce2693da-bc15-4253-ac5d-d3d44e68eb3e); Time taken: 0.07 seconds
INFO  : Executing command(queryId=hive_20170608083636_ce2693da-bc15-4253-ac5d-d3d44e68eb3e): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608083636_ce2693da-bc15-4253-ac5d-d3d44e68eb3e); Time taken: 0.139 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.339 seconds)
```