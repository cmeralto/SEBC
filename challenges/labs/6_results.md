```
CREATE ROLE politican1;
CREATE ROLE politician2;

GRANT ALL ON DATABASE default TO ROLE politican1;
GRANT ROLE politican1 TO GROUP conservative;

REVOKE ALL ON DATABASE default FROM ROLE politician2;
GRANT SELECT ON default.customers TO ROLE politician2;
GRANT SELECT ON default.sample_07 TO ROLE politician2;
GRANT SELECT ON default.sample_08 TO ROLE politician2;
GRANT SELECT ON default.web_logs TO ROLE politician2;
GRANT ROLE politician2 TO GROUP labour;
```

- theresa results
```
0: jdbc:hive2://ip-172-31-18-35.eu-west-1.com> show tables;
INFO  : Compiling command(queryId=hive_20170609110505_84c9c6fa-a29a-45fd-8265-7216fe986a2e): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170609110505_84c9c6fa-a29a-45fd-8265-7216fe986a2e); Time taken: 0.052 seconds
INFO  : Executing command(queryId=hive_20170609110505_84c9c6fa-a29a-45fd-8265-7216fe986a2e): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170609110505_84c9c6fa-a29a-45fd-8265-7216fe986a2e); Time taken: 0.11 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.183 seconds)
```


- jeremy results
```
[root@ip-172-31-18-35 ~]# sudo su - jeremy
[jeremy@ip-172-31-18-35 ~]$ kinit
Password for jeremy@CMERALTO.CO.UK:
[jeremy@ip-172-31-18-35 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.10.1 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-18-35.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-18-35.eu-west-1.compute.internal@CMERALTO.CO.UK
0: jdbc:hive2://ip-172-31-18-35.eu-west-1.com> show tables;
INFO  : Compiling command(queryId=hive_20170609110808_4a58ea72-0d1b-42ba-92e6-05146e7b7a41): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170609110808_4a58ea72-0d1b-42ba-92e6-05146e7b7a41); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20170609110808_4a58ea72-0d1b-42ba-92e6-05146e7b7a41): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170609110808_4a58ea72-0d1b-42ba-92e6-05146e7b7a41); Time taken: 0.137 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.31 seconds)
```