# HadoopCluster

- Architecture
  |SWITCH|10Gb Switch#1|10Gb Switch#2|10Gb Switch#3|10Gb Switch#4|
  |:------:|:-------------:|:-------------:|:-------------:|:-------------:|
  |HOST|Master#1|Master#2|Master#3|Master#4|
  |ZOOKEEPER|ZN#1|ZN#2|ZN#3||
  |HDFS|NN#1||NN#2||
  ||ZKFC#1||ZKFC#2||
  ||JN#1|JN#2|JN#3||
  |YARN|RM#1||RM#2||
  ||||Timeline Server||
  |MAPREDUCE||||HISTORY SERVER|
  |||MYSQL#1|MYSQL#2|MYSQL#3|
  |HIVE||METASTORE|METASTORE|METASTORE|
  |||HIVESERVER|HIVESERVER|HIVESERVER|
  |||||SPARK Master|

- S/W Version

  CentOS: 7.6

  Java: 1.8.0

  Ansible: 2.8.0

  Apache Hadoop: 3.2.4

  Zookeeper: 3.5.9

  Mysql: 5.7.53
  
  Hive: 3.1.2

  Tez: 0.9.1
  
- H/W Spec
  
  RACK: 50 ## rack-awareness.py 적용
  
  Server: 660 ea
  
  CPU: 80 / 48 / 32 Core = 25,440
  
  Memory: 168 TB
  
  
  
  
  
  
  
