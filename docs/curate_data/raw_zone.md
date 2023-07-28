# Data Curation

Once the data has landed in Fabric, the next step is to prepare the data for generating business value out of this. However raw data is  not always the best data to directly report on. This is information, which needs to be transformed for analysis by business users. In order to achieve this there has been an architectural pattern named [medallion architecture](https://learn.microsoft.com/en-us/azure/databricks/lakehouse/medallion), which has been widely adopted while building data platforms. 

On a high level, this pattern is all about landing your data into a zone that preserves the data in its native form. The second layer is about cleaning up the data to improve data quality and the final layer is where the data is modeled and made ready for consumption for business teams.

We will use a similar approach where data in its raw format is copied into the raw zone. The raw zone represents the data in its native format of the source. Examples of this are csv, avro,txt,parquet, xml,json etc. In the previous [blogs]() we did discuss 



