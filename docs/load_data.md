# Load Data

Loading data into your storage layer is the first step.  This could range from loading data from your local machine , or pulling data from your data centers / external file locations or other systems.This involves varying level of complexity , which could be as easy as a drag and drop , from your local file system to the storage or setting up complex data pipelines which could pull data. </br>

Working with customers over years , serving both these capabilites are equally important and impacts productivity. Fabric serves both these scenarios , by providng you easy interfaces to load your data from your local machine and also cater to creating complex data pipelines to extract the desired datasets. </br>

We will walk through both these scenarios. First one is the quick and easy way to get your data into onelake. </br>

## 

Microsoft Fabric offers Data Factory Component to load data from your sources into onelake. This could range from on-premise data sources (CRM systems/databases/ERP systems etc) , external data suppliers and even your own local machine. You could also use the [one lake file explorer](https://learn.microsoft.com/en-us/fabric/onelake/onelake-file-explorer) or the [lake house object explorer](https://learn.microsoft.com/en-us/fabric/data-engineering/navigate-lakehouse-explorer) in  fabric UI to upload files from your local machine to one lake directly. </br>

In many scenarios you might want to upload a local file and combine this with data coming in from other systems. These scenarios are enabled for you using Fabric. </br>

