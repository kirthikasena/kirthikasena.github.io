---
title: "Data pipeline for the research article trend analysis"
excerpt: "This project focuses on building a data pipeline for data exploratory in research articles on the
ArXiv website. The pipeline was built using the Hadoop ecosystem to give insight and for
reporting on the analysis of the dataset. In this particular analysis, Dataset was transferred to
HDFS in Hadoop which acts as a data lake. During the ETL process, This data is transformed
and processed into fact and dimension tables using pyspark. This processed data is stored in
the Hadoop hive, which acts as a pipeline sink. This data stored in the hive can later be read
for visualizing and Reporting."
collection: portfolio
---

###### Sophomore Year
<img src='/images/Screenshot 2023-08-03 at 11.33.39.png'>

##### Dataset 

This [dataset](https://www.kaggle.com/datasets/Cornell-University/arxiv)  consists of metadata in json format. This consists of about 3GB of data. The dataset
is the academic research-based domain. Arvix system’s data is still growing as the daily
research articles are higher than in previous days. There will be a need for a data pipeline to
provide insight effectively and for ample data storage.
Each research paper entry has information as follows:
(Id, submitter, authors, title, comment, categories, journelref, doi, abstract, categories,
update_date, versions).
3. Insight Generating Mechanism
Trying to achieve insights for reporting based on articles, The following questions can be
shown in visualizations as insights for the user to get an overall idea of the Arvix system’s
research articles.
1. Finding the most popular author in terms of articles published by the author:
• This can be achieved from the dataset’s column author and number of articles present
2. Day-wise count of articles being submitted and released after review
• This can be achieved from the dataset’s column updated date, and the day is split from
the date and number of articles present
3. Year-wise count of the number of articles submitted:
• This can be achieved by the year being split from date format and the count of articles
present
4. Finding articles based on the author’s name:
• This can be achieved by querying the author’s name and categories in the table created
from the dataset
5. Number of articles based on the categories or tags and category analysis distribution:
• This can be achieved by querying the category’s name and the number of articles in the
dataset
The dataset removes duplicates and missing values. The missing values in field title, id,
categories, and authors are removed as those are not valid data.

##### Pipeline Design
Selected Hortonworks Data Platform (HDP) 2.6.5 to be used for the whole pipeline as it has
inbuilt installations of each cluster and grouped in one place.
Sqoop is used to transform relational databases into HDFS; however, as this dataset is static
and in JSON format, sqoop can’t be used for ingestion flow from the local option. The dataset
doesn’t use come in real-time, or it doesn’t fall in the streaming data category. Therefore flume
or Kafka can’t be utilized in this case. The more appropriate way to consider ingestion is to use
WinSCP and put command: Hadoop fs -put (filename) (path of the required destination to be
stored) from maria dev user login or wget command with put command can be used to
download the dataset from the link.
Hadoop Distributed File System(HDFS) is used as the data lake; this is where the source from
the local system gets stored after ingestion flow. This acts as a backup for the dataset and
distributes large datasets for processing, and detects failure with the ability to recover on its
own. In addition, it is compatible with underlying operating systems.
During Extraction, Transforming, and loading, the dataset in HDFS is processed in pyspark.
Spark is an effective ETL tool for aggregating data and delivers clean data on unstructured
(JSON)or structured data. It also handles extensive data processing and is faster. Pyspark is
used as spark accessed with python as interface. The mechanisms are more familiar with python
than other programming languages to be used with a spark. This data set needs cleaning in
terms of removing missing values and removing duplicates. It also needs querying and splitting
to be done; to create a Fact and dimension table, pyspark is used.
This processed data is stored in the hive in the form of tables with columns. Hive is a more
suitable and powerful tool to play this role as it has the capacity of storing large tables of data
in the database. It also makes it easier for querying the data to bring out more insights for
reporting.
Orchestration mechanism can be done by oozie, which is previously installed in HDP like spark
and hive. Automating the data pipeline makes the process easier when handling extensive data,
as different jobs can be processed in the Hadoop ecosystem in one go. An attempt for Oozie
automation was made, but I couldn’t succeed in completing it.

##### Technical Implementation
Analyzing On-Prem+ Open-Source tools (Hadoop) with cloud platform-tools
On-Prem+Open source: Horton works Sandbox was installed with a virtual box on a windows
local machine.
Horton works were used as it has all clusters and tools in one place, whereas downloading each
tool separately(e.g., Hadoop spark,oozie) in the local machine can require time and space and
is not very effective. Hortonworks is a certified software from Apache with an open-source
license and is available for free use. At the same time, Cloudera is proprietary and sold in the
market and not fully open source. Although cloud services(AWS, GCP, Azure) have many
advantages compared to HDP on-prem such as scalability, elasticity, and more, this was chosen
as this amount of dataset(3Gb) that is currently being used works better on-prem as it doesn’t
require any credit information when compared to cloud services which need credit payment
after a period of time. There is no requirement on external factors such as the internet to access
your servers when using on-prem, unlike other cloud tools. There is complete control over the
ownership of configurations in HDP, whereas, in the cloud, the total ownership costs might be
higher than an upfront fee.
Framework comparison: Spark was used for data preprocessing rather than MapReduce in
the Hadoop ecosystem, as Apache spark is faster than map-reduce. Spark utilizes RAM and
works well with smaller datasets compared to map-reduce.
Programming language for Spark (ETL job): Python was chosen to be more suitable to
work with a spark. Although spark was selected to be faster and moderately easy to use, Python
is easier to use when compared to Scala.
[![](https://img.shields.io/badge/Python-white?logo=Python)](#) [![](https://img.shields.io/badge/Jupyter-white?logo=Jupyter)](#) [![](https://img.shields.io/badge/Tensorflow-white?logo=Tensorflow)](#)  

--- 
