# Data Curation 

Once the data has landed in Fabric, the next step is to prepare the data for generating business value out of this. However raw data is  not always the best data to directly report on. This is information, which needs to be transformed for analysis by business users. In order to achieve this there has been an architectural pattern named [medallion architecture](https://learn.microsoft.com/en-us/azure/databricks/lakehouse/medallion), which has been widely adopted while building data platforms. 

On a high level, this pattern is all about landing your data into a zone that preserves the data in its native form. The second layer is about cleaning up the data to improve data quality and the final layer is where the data is modeled and made ready for consumption for business teams.

We will use a similar approach where data in its raw format is copied into the raw zone. The raw zone represents the data in its native format of the source. Examples of this are csv, avro, txt,parquet, xml,json, etc. In the previous [blog](https://github.com/sarathsasidharan/fabric-launcher/blob/main/docs/load_data/load_data_scalable.md) we discussed on how fabric provides you easy options to load your data at scale. 

![raw_load](/images/raw_layer.png)

In the diagram above, Data factory is copying the data into a lakehouse item in fabric. [Lakehouse](https://learn.microsoft.com/en-us/fabric/data-engineering/lakehouse-overview) consists of Files and Tables folders on Onelake. Files folder represents the unstructured /unmanaged section of the lakehouse whereas Tables folder represents the structured section of the lakehouse. What does this mean , Files represent the section where files of any format (images , avro , csv, json,xml) could be housed, whereas the Tables section is to house the structured format.  The tables section provides you an awesome functionality, if your data is in delta lake format then it automatically provides a table on top of this data to query.We will discuss this more in the following blogs.

This construction makes it a good choice to house raw data in the Files folder of Lakehouse since this allows you to store the data in its raw form. Raw data undergoes transformation and cleaning to get into the second layer which is the silver layer. This layer is an entry point for data analysts and business users to start analyzing their datasets. In most cases, this is converted to a structured format and hence this can be a good candidate to be stored under the Tables folder in Lakehouse. As mentioned earlier as soon as the data lands here in [delta lake format](https://learn.microsoft.com/en-us/azure/synapse-analytics/spark/apache-spark-what-is-delta-lake), Fabric automatically converts this as a table for users to query on. 

There are different ways to organize your folders within the lakehouse folders, the same principles used in previous data platforms can be adopted here. An example is listed below.

![file_org](/images/rawzone_file.png)

In this section data is organized per day, this helps with better ways to isolate files and easily track the delivery of files from sources. The highest folder in this case is the department that might own this dataset, followed by the source which delivers this ( in this case point of sale), which is followed by year, month, and date. 

