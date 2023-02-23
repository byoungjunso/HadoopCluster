  # 대용량 하둡 플랫폼 설계 및 구축
- Cloudera Ambari Hadoop 구축
    - Erasure Coding(RS-6-3-1024K) 정책 적용
    - Cross realm authentication 적용으로 HDFS 클러스터간 데이터 교환 보안 강화
- 대용량 Apche Hadoop Eco System 구축 전환 개발
    - 연간 OPEX 비용 16억 -> 4억으로 절감
    - 신규 Hadoop Cluster 구성을 위한 N/W 및 Server 환경 설정
    - Ambari 운영 자동화 대체 환경(Ansible) playbook 작성
      + Data Decommission & Migration
      + 환경 구성 파일, library 변경 시 자동 배포
      + Ansible 을 활용한 서비스 재기동
    - Hadoop 모니터링 환경 개발
      + Volume Fail 알람 개발
      + Process Down 알람 개발
      + Long elapsed time Job 알람 개발
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
    - CentOS: 7.6
    - Java: 1.8.0
    - Ansible: 2.8.0
    - Apache Hadoop: 3.2.4
    - Zookeeper: 3.5.9
    - Mysql: 5.7.53
    - Hive: 3.1.2
    - Tez: 0.9.1
  
- H/W Spec
    - RACK: 50 ## rack-awareness.py 적용
    - Server: 660 ea
    - CPU: 80 / 48 / 32 Core = 25,440
    - Memory: 168 TB
  
 - 일 단위 데이터 적재량
    - 35 TB / 380억 record
  
  
  
