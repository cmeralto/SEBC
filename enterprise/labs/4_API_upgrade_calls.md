- Report the latest available version of the API
```
curl -u cmeralto:cloudera 'http://ec2-52-215-37-162.eu-west-1.compute.amazonaws.com:7180/api/version'
```
```json
v14
```

- Report the CM version
```
[root@ip-172-31-47-3 ~]# curl -u cmeralto:cloudera 'http://ec2-52-215-37-162.eu-west-1.compute.amazonaws.com:7180/api/v12/cm/version'
```
```json
{
  "version" : "5.9.2",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170330-1814",
  "gitHash" : "822da28bff818f57fc1bfc3eafe3a550300ef1b0",
  "snapshot" : false
}
```

- List all CM users
```
[root@ip-172-31-47-3 ~]# curl -u cmeralto:cloudera 'http://ec2-52-215-37-162.eu-west-1.compute.amazonaws.com:7180/api/v12/users'
```
```json
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "cmeralto",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
```

- Report the database server in use by CM
```

```
```json

```
