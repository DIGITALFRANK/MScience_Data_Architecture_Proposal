# MScience_Data_Architecture_Proposal




The purpose of this document is to outline and illustrate steps taken for configuring, automating, and optimizing M Science’s data architecture.  

The objective is to facilitate processes, increase performance and accuracy, and enable easy and efficient access to data by business users, data scientists, and analytics personnel, all the while minimizing costs.


By introducing new concepts of a Data Warehouse working besides a Data Lake (as opposed to data lake vs. data warehouse), we will be able to aggregate large sets of unstructured, semi-structured, and structured data at optimal scale, while at the same time warehousing critical operational and legally binding components into single-form entities for direct BI and Analysis.

Additionally, a hybrid multi-cloud approach to Data Infrastructure can be incorporated whereas Lake components will live on low availability hardware for cost consumption, and Warehouse components along with Computing components respectively will live on higher availability hardware for optimum performance.





## Data Lake + Data Warehouse = Data Agility

Any sort of file format, structured, semi-structured, and unstructured data can be dumped into the Data Lake.

In practice, multiple Data Warehouses can be implemented from a single Data Lake (AWS S3) and those warehouses keep two way ties to that lake, 

This approach ensures maximum performance and optimal cost-efficiency (which we will discuss later in this document).
[ architecture options vary, a single central Data Warehouse can be kept, with smaller Data Marts implemented to support it, or various Data Warehouses can be configured.  All reside in HDFS over and alongside the Data Lake ]

The various Data Warehouses will serve M Science’s various business needs as defined by industry or data specificity.

Despite the specificity of this warehouses, all data in the Lake (including its conjunctional Warehouses) can be accessed at any point and at any level by Business users and Data Scientists for BI and Analysis
*=> refer to the Data Lake VS Data Warehouse report by Dr Barry Devlin inside the “sources” folder for further details*



Additionally, any Operational RDBMS or NoSQL database used by M Science in its daily business realm can be attached to either the Data Lake or a Data Warehouse for real time or historical analysis.

Real-Time Data Streaming as well as Incremental Historical Data pipelines can also plugged into the DL or any of our DW’s or DM’s

I’m essence our Data Lake can take in data in any format, from any source, at any time, and move that data into its appropriate space (DW or DM or remaining for future use) or the process can happen in reverse










## Historical & Batch Data

Blah blah blah, blah blah

Hive tables



## Event Driven Data

The tweeterStream.py file is an example implementation of Spark Streaming that will inject real time Tweet data into our S3 Data Lake 

DStreams and subsequent RDD’s can be loaded into memory and examined at any time for a particular Tweeter sentiment, they can be outputted to a file and saved in the Hadoop file system (HDFS over S3) for future analysis 




## Operational Data

Blah, blah, blah

This is an example Apache Sqoop command to extract, clean & load data
=>

The following is a Sqoop command which will be scheduled and automated to retrieve incremental data from the operational RDBMS in real time, clean and load it into the appropriate Data Warehouse.
=>




## Containers and MicroServices

Finally, we will implement containers in our Computing to further isolate specific datasets or batch processes that serve unique business needs or are of specific relevance to Data Scientists.

The HortonWorks Enterprise Data Warehouse platform (EDW) along with Docker & Kubernetes are great tools to use in this scenario.
*=> refer to “rise of containers.pdf” document by Jane Doe inside the “sources” folder for more details* 



