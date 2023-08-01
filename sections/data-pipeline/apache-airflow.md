Apache Airflow
============
managed workflow orchestration service built on Apache Airflow with [Cloud Composer](https://cloud.google.com/composer?hl=en)
- [Create Cloud Composer](apache-airflow.md#Create-Cloud-Composer)
- [Import the Python Package](apache-airflow.md#Import-the-Python-Package)
- [Connected MySQL to Airflow](apache-airflow.md#Connected-MySQL-to-Airflow)

## Create Cloud Composer
1.Select your project<br>
2.Create the environment : " Composer 1 " 
<br> 
<br>
![1](/images/datapipeline/1.png)

3.SET UP Cloud Composer
- Name : _Your Project_
- Location : asia-east2 (it will use composer in HongKong)
- Image version : composer-1.20.12-airflow-2.4.3
- Node count : 3
- Zone : asia-east2-b
- Machine type : n1-standard-2
- Disk size (GB) : 30 _minimum_
- Number of schedulers : 1
![2](/images/datapipeline/2.png)

## Import the Python Package
Spectify libraries from the Python Package. 
- pymysql
- requests
- pandas

![3](/images/datapipeline/3.png)

## Connected MySQL to Airflow
![4](/images/datapipeline/4.png)













