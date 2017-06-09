- Command and output for hdfs dfs -ls /user
```
[root@ip-172-31-18-35 ~]# hdfs dfs -ls /user
Found 6 items
drwxrwxrwx   - mapred  hadoop                0 2017-06-09 09:44 /user/history
drwxrwxr-t   - hive    hive                  0 2017-06-09 09:45 /user/hive
drwxrwxr-x   - hue     hue                   0 2017-06-09 09:46 /user/hue
drwxr-xr-x   - jeremy  labour                0 2017-06-09 09:49 /user/jeremy
drwxrwxr-x   - oozie   oozie                 0 2017-06-09 09:46 /user/oozie
drwxr-xr-x   - theresa conservative          0 2017-06-09 09:48 /user/theresa
```

- The output from the CM API call ../api/v14/hosts
```
[root@ip-172-31-18-35 ~]# curl -u admin:celfocus2017 'ec2-54-72-9-49.eu-west-1.compute.amazonaws.com:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "14e977ee-942a-42b5-a5ea-f0444d7d92f5",
    "ipAddress" : "172.31.18.35",
    "hostname" : "ip-172-31-18-35.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-18-35.eu-west-1.compute.internal:7180/cmf/hostRedirect/14e977ee-942a-42b5-a5ea-f0444d7d92f5",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740506112
  }, {
    "hostId" : "5fb6ba9b-eaa4-4a2d-954f-163be96ce960",
    "ipAddress" : "172.31.20.160",
    "hostname" : "ip-172-31-20-160.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-18-35.eu-west-1.compute.internal:7180/cmf/hostRedirect/5fb6ba9b-eaa4-4a2d-954f-163be96ce960",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740506112
  }, {
    "hostId" : "e778a5f8-3a03-4804-891a-cb1e1dc3d34c",
    "ipAddress" : "172.31.21.17",
    "hostname" : "ip-172-31-21-17.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-18-35.eu-west-1.compute.internal:7180/cmf/hostRedirect/e778a5f8-3a03-4804-891a-cb1e1dc3d34c",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740506112
  }, {
    "hostId" : "dd3b1503-3523-45c4-b8e0-aa702066fc7b",
    "ipAddress" : "172.31.27.21",
    "hostname" : "ip-172-31-27-21.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-18-35.eu-west-1.compute.internal:7180/cmf/hostRedirect/dd3b1503-3523-45c4-b8e0-aa702066fc7b",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740506112
  }, {
    "hostId" : "b2d4b555-f059-42d9-9aa8-73f9f6d9071e",
    "ipAddress" : "172.31.28.201",
    "hostname" : "ip-172-31-28-201.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-18-35.eu-west-1.compute.internal:7180/cmf/hostRedirect/b2d4b555-f059-42d9-9aa8-73f9f6d9071e",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740506112
  } ]
}
```