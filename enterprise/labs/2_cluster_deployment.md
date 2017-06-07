Command: [root@ip-172-31-47-3 ~]# curl -u cmeralto:cloudera http://ec2-52-215-37-162.eu-west-1.compute.amazonaws.com:7180/api/v2/cm/deployment

```json
{
  "timestamp" : "2017-06-07T12:49:14.175Z",
  "clusters" : [ {
    "name" : "Cluster cmeralto",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "644874240"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "644874240"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "912680550"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "153"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-46-176.eu-west-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "password"
        }, {
          "name" : "hive_metastore_database_user",
          "value" : "metastore"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-79de62484ef66ab702e3c28a075030ca",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-01eb184da7d776ae5"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-bbabac3496aa0d0affd6b25934e342dc",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-03176902a72eda324"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5neilkw8qehhsg7ewg96oshzf"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-bbabac3496aa0d0affd6b25934e342dc",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-03176902a72eda324"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2f7bty1uvm3r0hmc9029hsnko"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "644874240"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-71cf1fea2ee5e971c4b13e3d11b281b5",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-03e077f205e6d0582"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bcw08tni9obci0zdi4nlh96k2"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-92c0fee6dc801e9a631d1476eea421c3",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0672734db8efc56d4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9tqb43h8bl6tjyrabdxwcjc50"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-bbabac3496aa0d0affd6b25934e342dc",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-03176902a72eda324"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "92rtm986utordup7kkymzu2oh"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-46-176.eu-west-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "huepassword"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-bbabac3496aa0d0affd6b25934e342dc"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-bbabac3496aa0d0affd6b25934e342dc",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-03176902a72eda324"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d38kuib6oswdotzpea1n4dnj2"
          }, {
            "name" : "secret_key",
            "value" : "PlSPztMLFH8AHa3eTzUND5g6gvKJ9X"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-46-176.eu-west-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "644874240"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-bbabac3496aa0d0affd6b25934e342dc",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-03176902a72eda324"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ew4lancrkrrpsa7apu47tn361"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/01/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/data/01/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "5250"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "5250"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "5f2LArZwQQTPGg9egjaYzAvaL6C4wY"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-71cf1fea2ee5e971c4b13e3d11b281b5",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-03e077f205e6d0582"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "f3viqhtv2i0dql3vmm8nvgl8x"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-79de62484ef66ab702e3c28a075030ca",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-01eb184da7d776ae5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "545h4y155tfgagcl83uur741d"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-adf6860f174384714c6fd62684831f86",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-02d8bace2cfa01dfa"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "imroed03k7aooqka7jljgy6r"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-bbabac3496aa0d0affd6b25934e342dc",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-03176902a72eda324"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "xn5hvfbis7yls57mfpish8r7"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-71cf1fea2ee5e971c4b13e3d11b281b5",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-03e077f205e6d0582"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "42"
          }, {
            "name" : "role_jceks_password",
            "value" : "12yuxo5c9o3gm1j0shewxirwi"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/data/01/dfs/dn"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/data/01/jn/"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "kOjWUYbtlnBh0Km137avSe3XZGKolw"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "4tnHXlaEcGyHmHoCsfBzcNytWyrUCM"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "diEGsDCj9wGd8EXH0xtulkbl01YP6D"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-71cf1fea2ee5e971c4b13e3d11b281b5",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-03e077f205e6d0582"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-79de62484ef66ab702e3c28a075030ca",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-01eb184da7d776ae5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "fkl3peio7gcdk52ykpgo4l77"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-adf6860f174384714c6fd62684831f86",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-02d8bace2cfa01dfa"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cizd3cfjakv0thwrnqt41thy2"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-bbabac3496aa0d0affd6b25934e342dc",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-03176902a72eda324"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eihy5jrgndwdvnhrj4xe5kq9g"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-71cf1fea2ee5e971c4b13e3d11b281b5",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-03e077f205e6d0582"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "289vkwoakadxu7xbw0qbhcn0u"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-92c0fee6dc801e9a631d1476eea421c3",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0672734db8efc56d4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5il29qu513k5qloahv7m00nf9"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-bbabac3496aa0d0affd6b25934e342dc",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-03176902a72eda324"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "92vhaqy58un4qyrnkoxxg5v3o"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-71cf1fea2ee5e971c4b13e3d11b281b5",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-03e077f205e6d0582"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dfq59hv8pcd58jhhd5nm045sb"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-92c0fee6dc801e9a631d1476eea421c3",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0672734db8efc56d4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9oy5rntgvgd5i5xqqo7edqbxk"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-bbabac3496aa0d0affd6b25934e342dc",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-03176902a72eda324"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6kth4eq6pxvdybobrrgua4xoa"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-71cf1fea2ee5e971c4b13e3d11b281b5",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-03e077f205e6d0582"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "44"
          }, {
            "name" : "role_jceks_password",
            "value" : "cqlnumlc5bziv1lg7vkqyqjdv"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-92c0fee6dc801e9a631d1476eea421c3",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0672734db8efc56d4"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "56"
          }, {
            "name" : "role_jceks_password",
            "value" : "8dzkn45eytko28rzrq4485ivb"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-02d8bace2cfa01dfa",
    "ipAddress" : "172.31.32.24",
    "hostname" : "ip-172-31-32-24.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-03e077f205e6d0582",
    "ipAddress" : "172.31.36.205",
    "hostname" : "ip-172-31-36-205.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0672734db8efc56d4",
    "ipAddress" : "172.31.37.163",
    "hostname" : "ip-172-31-37-163.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-01eb184da7d776ae5",
    "ipAddress" : "172.31.46.176",
    "hostname" : "ip-172-31-46-176.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-03176902a72eda324",
    "ipAddress" : "172.31.47.3",
    "hostname" : "ip-172-31-47-3.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__edd99297-d214-4d97-a4d3-5860dc0d2ce0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "38cdca75af6873e126f207562186e3186cf35c61ab1defdec012a71fa3c769b5",
    "pwSalt" : 7501774720365459343,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-bbabac3496aa0d0affd6b25934e342dc",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "758950b8386f1c2f2f3cd9e2b53b9d3083956710536a82554e28a0e6daf40992",
    "pwSalt" : 8703976134293049506,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-bbabac3496aa0d0affd6b25934e342dc",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "16956e7893bacddcfd03166f08fe1b27df7d30e35348bb80cc33b01b2484f5a5",
    "pwSalt" : 8451034420064766517,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-bbabac3496aa0d0affd6b25934e342dc",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "6b9b9abac104a3de83485f05ac312e57b72026efc1289bf7bec12e476b2144a7",
    "pwSalt" : -2660241437776805192,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-bbabac3496aa0d0affd6b25934e342dc",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "0650a6b1216b065e2e39ea7417d4ee431a99d0941d490a9e8e69f11157dfe15c",
    "pwSalt" : -5035174664380478185,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "99cdbd2011198f3573ec552867fd2f26757c8d00f5beb8269c14ed243059039b",
    "pwSalt" : -8502927460673419427,
    "pwLogin" : true
  }, {
    "name" : "cmeralto",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "5148bba88d6c150f61fa81d29fd6091bb2fd0f22e2a0ca7e516532c3960c5151",
    "pwSalt" : -8503695331144013920,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "576d2c7c0ffaf454788c1ffb9b286d08658a9f4cfd850afdf89fa53e8260397e",
    "pwSalt" : -8731117233999823220,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1014",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "644874240"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "644874240"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "837812224"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-46-176.eu-west-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "644874240"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "644874240"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "837812224"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-bbabac3496aa0d0affd6b25934e342dc",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-03176902a72eda324"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8uhkztcsvlp6v0ujeaohxpigd"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-bbabac3496aa0d0affd6b25934e342dc",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-03176902a72eda324"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8xehcympuxnjh712seke963mi"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-bbabac3496aa0d0affd6b25934e342dc",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-03176902a72eda324"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2586jh6krc5jn5z31m3cg9l38"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-bbabac3496aa0d0affd6b25934e342dc",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-03176902a72eda324"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2wzluxqay4kjgiiegrexrc540"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-bbabac3496aa0d0affd6b25934e342dc",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-03176902a72eda324"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2mxuv6vu6vmx8t7uwfr7um8a3"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/23/2012 23:40"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/5.8.3/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
```