Apache Airflow
============
managed workflow orchestration service built on Apache Airflow with [Cloud Composer](https://cloud.google.com/composer?hl=en)
<br>

[Create Cloud Composer](apache-airflow.md#Create-Cloud-Composer)
- [Import the Python Package](apache-airflow.md#Import-the-Python-Package)
- [Connected MySQL to Airflow](apache-airflow.md#Connected-MySQL-to-Airflow)

Data Lake
============
managed service for storing unstructured data with 
[Google Cloud Storage](https://cloud.google.com/storage)


[Create Google Cloud Storage](apache-airflow.md#Create-Google-Cloud-Storage)
- [Upload files to GCS](apache-airflow.md#Upload-files-to-GCS)
- [Automate Tasks With Airflow](apache-airflow.md#Automate-Tasks-with-Airflow )

Data Warehouse
============
builded the Data warehouse with [BigQuery](https://cloud.google.com/bigquery)
- [Create Data set of BigQuery](apache-airflow.md#Create-Data-set-of-BigQuery )


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
<br>

![2](/images/datapipeline/2.png)

## Import the Python Package
Spectify libraries from the Python Package. 
- pymysql
- requests
- pandas

![3](/images/datapipeline/3.png)

## Connected MySQL to Airflow
click Admin and select Connections
- Host : _The host to connect_
- Schema : _Specify the schame name to be used in the database_
- Login : _Specify the user name to connect_
- Password : _your host password_
- Port : _MySQL port_ 
<br>

![4](/images/datapipeline/4.png)


## Create Google Cloud Storage
When you create a Cloud Composer environment, Google Cloud Storage will automatically create a bucket that is connected to the environment.

## Create Data set of BigQuery
1. Open Google BigQuery
2. Create data set
- Select : the project
- Fill : _the data set ID_
- Location type : _Region_
- Region : _asia-east2(Hong Kong)_
<br>

![10](/images/datapipeline/10.png)



## Upload files to GCS
1. Open Cloud Shell in Google Cloud Storage, Upload files  
2. Files : _Airflow DAG definition file_
<br>

![5](/images/datapipeline/5.png)

3. [My Airflow DAGS File](sections/data-pipeline/au_bk_load2.py)
- Task1 : PythonOperator - get data from database
- Task2 : PythonOperator - get REST API
- Task3 : PythonOperator - merge data from transaction path and conversion path
- Task4 : GCSToBigQueryOperator - Upload output path to Data Warehouse (BigQuery)
<br>

![8](/images/datapipeline/8.png) 
   
4. Upload to GCS using gsutil command : [ $ gsutil cp _DAGS files_ gs:// _BUCKET_ / _folder_ ]
<br>

![6](/images/datapipeline/6.png)

## Automate Tasks with Airflow
Open Cloud Composer it shows your environment.
<br>
<br>
1.Click "_OPEN AIRFLOW UI_ "<br>
2.Select the environment in Airflow 
<br>

![7](/images/datapipeline/7.png)

3.Open Google BigQuery<br> 
4.Select the Data set. it will show the table from Task4.  
<br>

![9](/images/datapipeline/9.png)

<p align="center">this table has 1.9 million rows </p>








     









