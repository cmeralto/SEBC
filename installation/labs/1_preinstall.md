1. Check vm.swappiness on all your nodes (Set the value to 1 if necessary)

```
[root@ip-172-31-46-176 ~]# sysctl vm.swappiness
vm.swappiness = 60

[root@ip-172-31-46-176 ~]# sysctl vm.swappiness=1
vm.swappiness = 1

[root@ip-172-31-46-176 ~]# sysctl vm.swappiness
vm.swappiness = 1
```

To configure swapiness to 1 permanent:

<code>sudo bash -c "echo 'vm.swappiness = 1' >> /etc/sysctl.conf"</code>

