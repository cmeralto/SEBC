1 - Write curl statements that stop, start, and check the current state of your Hive service. 

- Stop
```
[root@ip-172-31-47-3 ~]# curl -X POST -H "Content-Type:application/json" -u cmeralto:cloudera 'http://ec2-52-215-37-162.eu-west-1.compute.amazonaws.com:7180/api/v12/clusters/Cluster%20cmeralto/services/hive/commands/stop'
```
```json
{
  "id" : 562,
  "name" : "Stop",
  "startTime" : "2017-06-07T13:17:25.846Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

- Start
```
[root@ip-172-31-47-3 ~]# curl -X POST -H "Content-Type:application/json" -u cmeralto:cloudera 'http://ec2-52-215-37-162.eu-west-1.compute.amazonws.com:7180/api/v12/clusters/Cluster%20cmeralto/services/hive/commands/start'
```
```json
{
  "id" : 566,
  "name" : "Start",
  "startTime" : "2017-06-07T13:19:45.479Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

- Check status
```
[root@ip-172-31-47-3 ~]# curl -u cmeralto:cloudera 'http://ec2-52-215-37-162.eu-west-1.compute.amazonaws.com:7180/api/v12/clusters/Cluster%20cmeralto/services/hive/' | grep serviceState
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
112   785    0   785    0     0  13691      0 --:--:-- --:--:-- --:--:-- 16354
  "serviceState" : "STARTED"
```