# Hadoop-Spark 쇼핑몰 고객행동 데이터 분석

> 개인 프로젝트

![image](https://github.com/OhJune/Hadoop-Spark/assets/124857930/bf2d60bd-a6cc-41b4-9294-54d8365f98a6)


    * 시간대별, 주말/평일별 등 spark 전처리,분석 후 sparkML로 개인화 추천시스템 구축

    * 데이터 수집,적재 HDFS (DW) -> 데이터 전처리 Spark, SparkML -> BigQuery (DM) -> 시각화 

### ✏️사용스택
---

<img src="https://img.shields.io/badge/apachehadoop-66CCFF?style=for-the-badge&logo=apachehadoop&logoColor=black">  <img src="https://img.shields.io/badge/apachespark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=black">
<img src="https://img.shields.io/badge/ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=black">
<img src="https://img.shields.io/badge/tableau-E97627?style=for-the-badge&logo=tableau&logoColor=black">



### 🐘Hadoop Cluster 서버 구축 
---

총 8개 노트북으로 Hadoop cluster 구축

      운영 체제 : Ubuntu22.04

      haddop 구성 : client , namenode, secondnode, datanode1, datanode2, datanode3, datanode4, datanode5

<p align="center">
<img src = "https://github.com/OhJune/Hadoop-Spark/assets/124857930/b45441a2-e515-4529-80bb-1cb5cb61a762" width="600" height="600">
</p>


* 각 각의 노트북은 ssh키로 연결
   * ssh 퍼블릭 키를 1개로 모아서 모든 노드에 전달
   * 총 8대의 노드들 모두 생성 후 ssh키를 공유하고서 하나의 authorized_keys로 생성 후 전달
   * vim /etc/hosts : hosts파일에 각 노드들의 고정 ip 추가
* ufw 리눅스 방화벽을 중지하였습니다. ufw방확벽 때문에 클러스트 간의 데이터 통신이 제한됨.
* 각 노드들에게 고정 ip를 통해서 client에서 네트워크 통신을 설정.
  <p align="center">
  <img src = "https://github.com/OhJune/Hadoop-Spark/assets/124857930/e7d6c214-f4de-4618-98c9-873410738f0c" width="300" height="300"/>
  </p>

### ⭐Spark 
---

* 주피터 서버에서 pyspark 커널을 통해서 Sparksession을 연결. 커널은 cpu의 자원할당문제로 인해 2개만 생성
* 전처리 후 데이터 EDA와 집계 테이블 생성 후 Bigquery에 저장, 간단한 시각화
* SparkML의 분류분석 모델링 


### 📁데이터 설명
---

`대규모 온라인 종합 쇼핑몰의 7개월 동안의 행동 데이터` 

<div style="float:left; width:40%; margin-right:10px;">
  <div markdown="1">

  |  컬럼명 | 컬럼설명 |
  |--|--|
  | **`event_time`** | 이벤트 발생 시간 |
  | **`event_type`** | 이벤트 유형 |
  | **`product_id`** | 상품 id |
  | **`category_id`** | 카테고리 id |
  | **`category_code`** | 카테고리 분류 |
  | **`brand`** | 브랜드명 |
  | **`price`** | (상품)가격 |
  | **`user_id`**| 유저 id |
  | **`user_session`** | 유저 세션 |

  </div>
</div>



  


