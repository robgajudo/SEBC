* No result using the user robgajudo since it only has the User Administrator Role
```
[ec2-user@ip-172-31-3-11 ~]$ curl -u robgajudo:cloudera "http://54.254.163.92:7180/api/v2/cm/deployment"
```
* Used admin user as Cluster Administrator
```
[ec2-user@ip-172-31-3-11 ~]$ curl -u admin:admin "http://54.254.163.92:7180/api/v2/cm/deployment"
{
  "timestamp" : "2016-12-07T03:39:48.351Z",
  "clusters" : [ {
    "name" : "RobGajudo",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "606076928"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "606076928"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3525941657"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "593"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-3-11.ap-southeast-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "welcome1"
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
        "name" : "hive-GATEWAY-28e75a94ea72223ae359979962d0feb5",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-12fa3bb5"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-3f584b132f30d2e993191e1748d332df",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-10fa3bb7"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-b6d357f9bedf4699884b5a16029200dc",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-11fa3bb6"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-e791395f764f9d954aa83e5f5d85ce70",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-13fa3bb4"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dh4dbglpx5b6mod8k4z97rl00"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7ir7qcpybz4mhwj611cwingjc"
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
            "value" : "606076928"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-28e75a94ea72223ae359979962d0feb5",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-12fa3bb5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "acth3d0oi0irayd10x5jp67c9"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cdchkwa98mnlfvwx3q4xyldd7"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-e791395f764f9d954aa83e5f5d85ce70",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-13fa3bb4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "34il8hnm2elsxqxy2penb9rzm"
          }, {
            "name" : "serverId",
            "value" : "1"
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
          "value" : "ip-172-31-3-11.ap-southeast-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "welcome1"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-62c2907d1a66dd0c935fbbf66af5e7ff"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2htw7z7m6c0rv4p1cvtqg4hmh"
          }, {
            "name" : "secret_key",
            "value" : "m2uxmqYK7itrOMQUU0gSxTx7veEa2R"
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
            "value" : "ip-172-31-3-11.ap-southeast-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "welcome1"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "606076928"
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
        "name" : "oozie-OOZIE_SERVER-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "aam2itajtljttlyt6jxy7w8vq"
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
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "606076928"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "4"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "3730"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "606076928"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "5147"
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
          "value" : "OUKPrreQ4VEROTN0ycMK1IVm1W4Iti"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1vgj9tk5nzuzh1marzc4rznfz"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-28e75a94ea72223ae359979962d0feb5",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-12fa3bb5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3481n2ydoxrfqh51eo9vstn6o"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-3f584b132f30d2e993191e1748d332df",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-10fa3bb7"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9tuk33lo4uihkencclonz43tg"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-b6d357f9bedf4699884b5a16029200dc",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-11fa3bb6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4vogcar6kvbn82j1sl9rl90vz"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-e791395f764f9d954aa83e5f5d85ce70",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-13fa3bb4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "aed4f1rl4i7krev85z63nvfi"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "53"
          }, {
            "name" : "role_jceks_password",
            "value" : "sqcwpun45lyuij1qihag6lw3"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "606076928"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "3382062284"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
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
            "value" : "/dfs/journal"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "606076928"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "606076928"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "yIw5cHDwzTCBR4uWYnq21qpWMAs8L9"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "njQsf45XxsPd8YRFOnaUr2tKyHTnFJ"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "4pBNjDUkQsMJfFkmdtpcBeqerfSXWa"
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
        "name" : "hdfs-BALANCER-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-28e75a94ea72223ae359979962d0feb5",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-12fa3bb5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bkag2mgvjaughtf7qauee7ia"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-3f584b132f30d2e993191e1748d332df",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-10fa3bb7"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dhr5866y8fq0ky45mlyqq0coz"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-b6d357f9bedf4699884b5a16029200dc",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-11fa3bb6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5rqwcnyao5w8ioem87zq6h55r"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-e791395f764f9d954aa83e5f5d85ce70",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-13fa3bb4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "374um9x2qdmhnmtyy4d2xdeor"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5ypbdex5tb35jpojtjrkpgtih"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-e791395f764f9d954aa83e5f5d85ce70",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-13fa3bb4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8n5b2essrihxqrggj2rrfid7j"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-28e75a94ea72223ae359979962d0feb5",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-12fa3bb5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1zm50zcdutimc122gi46ulu5d"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5fb88jagnwq5xz77o3m5qkfc2"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-e791395f764f9d954aa83e5f5d85ce70",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-13fa3bb4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "14y8z065x79a1d3rrfrq797zt"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-62c2907d1a66dd0c935fbbf66af5e7ff",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0cfa3bab"
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
            "value" : "55"
          }, {
            "name" : "role_jceks_password",
            "value" : "afzuby4a7mpw9km5n3q4stdve"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-e791395f764f9d954aa83e5f5d85ce70",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-13fa3bb4"
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
            "value" : "61"
          }, {
            "name" : "role_jceks_password",
            "value" : "amngf37iym39ii3wv9mh4s2l3"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-0cfa3bab",
    "ipAddress" : "172.31.3.11",
    "hostname" : "ip-172-31-3-11.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-13fa3bb4",
    "ipAddress" : "172.31.3.12",
    "hostname" : "ip-172-31-3-12.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-12fa3bb5",
    "ipAddress" : "172.31.3.13",
    "hostname" : "ip-172-31-3-13.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-11fa3bb6",
    "ipAddress" : "172.31.3.14",
    "hostname" : "ip-172-31-3-14.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-10fa3bb7",
    "ipAddress" : "172.31.3.15",
    "hostname" : "ip-172-31-3-15.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_CLUSTER_ADMIN" ],
    "pwHash" : "385a7120e52747f636e983d50f1ce4429e7f40d48df1b11c06b8c9ca60bd4def",
    "pwSalt" : 7261733994477669704,
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
          "value" : "606076928"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "606076928"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-3-11.ap-southeast-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "welcome1"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "606076928"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "606076928"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-62c2907d1a66dd0c935fbbf66af5e7ff",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-0cfa3bab"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "4ajutnk1setm491t1gc60a8mx"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-62c2907d1a66dd0c935fbbf66af5e7ff",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-0cfa3bab"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ygnh31gbnx56n7hx1fluql2s"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-62c2907d1a66dd0c935fbbf66af5e7ff",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-0cfa3bab"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "b3d5fadofigp1x75nd3mf5d89"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-62c2907d1a66dd0c935fbbf66af5e7ff",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-0cfa3bab"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "abbux1g2wmv8uynql97op53uq"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-62c2907d1a66dd0c935fbbf66af5e7ff",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-0cfa3bab"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2xs59cyctoqsd000top49yyp7"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/24/2012 16:20"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}[ec2-user@ip-172-31-3-11 ~]$
```
