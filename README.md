# MScience_Data_Architecture_Proposal




The purpose of this document is to outline and illustrate steps taken for configuring, automating, and optimizing M Science’s data architecture.  

The objective is to facilitate processes, increase performance and accuracy, and enable easy and efficient access to data by business users, data scientists, and analytics personnel, all the while minimizing costs.


By introducing new concepts of a Data Warehouse working besides a Data Lake (as opposed to data lake vs. data warehouse), we will be able to aggregate large sets of unstructured, semi-structured, and structured data at optimal scale, while at the same time warehousing critical operational and legally binding components into single-form entities for direct BI and Analysis.

Additionally, a hybrid multi-cloud approach to Data Infrastructure can be incorporated whereas Lake components will live on low availability hardware for cost consumption, and Warehouse components along with Computing components respectively will live on higher availability hardware for optimum performance.





## Data Lake + Data Warehouse = Data Agility


# My man, it seems more like it would be the "Data Lake" living inside the "Data Warehouse"

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







## Hibryd Multi-Cloud Architecture

The following documentation by Google Cloud examines multi-cloud patterns and best practices.  The objective is to minimize cost by carefully arranging architecture components in the right place, for the right purpose, for the best performance, at the lowest cost: https://cloud.google.com/solutions/hybrid-and-multi-cloud-patterns-and-practices







## Historical & Batch Data

Blah blah blah, blah blah

The data currently residing in the Data Lake, or previously aggregated data will fall into the category of Historical or Batch Data,
Though that data is available for a variety of users at any level and anytime, there are steps we can and should take to further the agility of the data, as well as increase ease of querying and the performance of such.



Hive tables, for example customer behavioral data partitioned by state



## Event Driven Data

The tweeterStream.py file is an example implementation of Spark Streaming that will extract real time Tweet data using Transmission Control Protocol (TCP).
When run in a Spark environment, this Python script will keep a real time stream of all tweets that include the word 'M Science'.  Those tweets are loaded into Resiliant Distributed DataSets (RDD's), that can either be evaluated and analysed in-memory, or outputted to a file and stored into our AWS S3 Data Lake (HDFS)  

Spark Discretized Streams (DStreams) and subsequent RDD’s can be loaded into memory and examined at any time for a particular Tweeter sentiment, they can be outputted to a file and saved in the Hadoop file system (HDFS over S3) for future analysis.  In the above mentioned Python file, any keyword or Regular Expression (RegEX) can replace the word 'M Science', and tweets containing those strings will be streamed instead.  

In essence, this scenario allows us to aggregate public sentiment data on any particular subject in real time, and allows Data Scientists to perform direct analysis on that data, or increment and store such data for future use.

The above can be applied to any social media network and yield similar results 




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



