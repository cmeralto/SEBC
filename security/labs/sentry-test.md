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
