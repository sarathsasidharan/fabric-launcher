# Data Curation

Once the data has landed in Fabric, the next step is to prepare the data for generating business value out of this. However raw data is always not always the best data to directly report on. This is actually information, which needs to be transformed into intelligence. In order to achieve this there has been an architectural pattern named [medallion architecture](https://learn.microsoft.com/en-us/azure/databricks/lakehouse/medallion), which has been widely adopted while building data platforms.

We will use a similar approach where data in its raw format is copied into the raw zone. On Fabric, this could be a Folder 
