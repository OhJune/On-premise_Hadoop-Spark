# Hadoop-Spark 쇼핑몰 로그 데이터 분석

> 개인 프로젝트

![image](https://github.com/OhJune/Hadoop-Spark/assets/124857930/bf2d60bd-a6cc-41b4-9294-54d8365f98a6)


    * 시간대별, 주말/평일별 등 spark 전처리,분석 후 sparkML로 개인화 추천시스템 구축

    * 데이터 수집,적재 HDFS (DW) -> 데이터 전처리 Spark, SparkML -> BigQuery (DM) -> 시각화 

### Hadoop Cluster 서버 구축 

총 8개 노트북으로 Hadoop cluster 구축

      운영 체제 : Ubuntu22.04

      haddop 구성 : client , namenode, secondnode, datanode1, datanode2, datanode3, datanode4, datanode5

<p align="center">
<img src = "https://github.com/OhJune/Hadoop-Spark/assets/124857930/b45441a2-e515-4529-80bb-1cb5cb61a762" width="600" height="600">
</p>


* 각 각의 노트북은 ssh키로 연결하였습니다.
   * ssh 퍼블릭 키를 1개로 모아서 모든 노드에 전달
   * 총 8대의 노드들 모두 생성 후 ssh키를 공유하고서 하나의 authorized_keys로 생성 후 전달
   * vim /etc/hosts : hosts파일에 각 노드들의 고정 ip 추가
* ufw 리눅스 방화벽을 중지하였습니다. ufw방확벽 때문에 클러스트 간의 데이터 통신이 제한됨.
* 각 노드들에게 고정 ip를 통해서 client에서 네트워크 통신을 설정.
  <p align="center">
  <img src = "https://github.com/OhJune/Hadoop-Spark/assets/124857930/e7d6c214-f4de-4618-98c9-873410738f0c" width="300" height="300"/>
  </p>

### Spark 


