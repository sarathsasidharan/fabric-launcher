# Data Curation

Once the data has landed in Fabric, the next step is to prepare the data for generating business value out of this. However raw data is always not always the best data to directly report on. This is actually information, which needs to be transformed into intelligence. In order to achieve this there has been an architectural pattern named [medallion architecture](https://learn.microsoft.com/en-us/azure/databricks/lakehouse/medallion), which has been widely adopted while building data platforms.

We will use a similar approach where data in its raw format, from the source system,  is copied into the raw zone. On Fabric, this is a folder in the /Files section where we store the data in its raw form. As discussed in the previous blogs Fabric provides you easy options to load data at scale. To help you navigate with choices, refer to the [decision document](https://learn.microsoft.com/en-us/fabric/get-started/decision-guide-pipeline-dataflow-spark#copy-activity-dataflow-and-spark-properties) which helps you map which tooling is best fit for loading your data.


