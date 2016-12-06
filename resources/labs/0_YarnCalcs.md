Adjustment made in YARNCalcs

* First thing I noticed is that as you consume more Memory/CPU and assigned it to the OS, NodeManager, DataNode, Impalad, CM Agent, HBase, and Solr the lesser the Yarn resources that you can use.
* Adjusted the OS Memory formula to 7% of the total Memory since most of the OS only used 4-8 GB as minimum
* Also adjusted the OS CPU to 1
* Set 16GB RAM for Impala Processes since Impala is Memory intensive.
* The minimum for the mapreduce.map.memory.mb depends on the alloated yarn.nodemanager.resource.memory-mb of the NameNode divided by the mapreduce.map.memory.mb set in the Task Container Settings.
* The minimum for the mapreduce.map.cpu.vcores depends on the allocated yarn.nodemanager.resource.cpu-vcores of the NameNode divided by the mapreduce.map.cpu.vcores set in the Task Container Settings.
* Criterias that affects the workload factor are network throughput, rack awaraness configuration, skewed data, different services using the cluster. 
* What does a value of 1, 2, or 4 signify?
As you increase the workload factor the number of map and reduce jobs also increases as it refers to the number of CPU needed. It points out that the higher the value the more CPU intesive the workload is.
