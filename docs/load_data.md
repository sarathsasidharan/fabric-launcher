# Load Data

Loading data into your storage layer is the first step.  This can repesent varying levels of complexity which could be loading data from your local machine to more complicated ones like pulling data from your data centers / external file locations / other systems. </br>

Working with customers over years , serving both these capabilites are equally important and impacts productivity. Fabric serves both these scenarios , by providng you easy interfaces to load your data from your local machine and also cater to creating complex data pipelines to extract the desired datasets. </br>

We will walk through both these scenarios. First one is the quick and easy way to get your data into onelake. </br>

## Ad-hoc Data Loading Scenarios
We did talk about OneLake as being our "one drive for data". In order to load data into your OneLake , we need to create an item [lakehouse](https://learn.microsoft.com/en-us/fabric/data-engineering/lakehouse-overview) within your Fabric workspace.This creates an item for you to load the data. There are two folders , namely the Files and Tables. The Files folder represent the unmanaged section of your lakehouse and Tables represents the managed area. Files section is where all data (structured / unstructured / semi-structured) in any format could land. Tables represents the structured data.</br>

Fabric UI , provides you an easy option to upload a file / folder into your OneLake. You can browse your local file system and load the folder / file containing the data which needs to be analyzed. Using this option you can upload any file /folder into the Files section. Note that this option is only available for Files and not Tables. The reason for this , as we discussed earlier is that Files folder is the unmanaged area , which allows you to load data of any format /type.

![upload_data](/images/load-easy.png)

Another amazing utility Fabric provides is the [One Lake File Explorer](https://learn.microsoft.com/en-us/fabric/onelake/onelake-file-explorer). This gives you the real look and feel of "one drive for data" where you can view / download / upload any folder / file from your local filesystem.  

![one_lake_file_explorer](/images/onelake-file-explorer.png) 

The third option for users familiar with azure , there is also support for [Azure Storage Explorer](https://learn.microsoft.com/en-us/fabric/onelake/onelake-azure-storage-explorer).This provides you the ability to connet to a Lakehouse item and view / download / upload files or folders. 

## Scalable Data Loading Scenarios


Microsoft Fabric offers Data Factory Component to load data from your sources into onelake. This could range from on-premise data sources (CRM systems/databases/ERP systems etc) , external data suppliers and even your own local machine. You could also use the [one lake file explorer](https://learn.microsoft.com/en-us/fabric/onelake/onelake-file-explorer) or the [lake house object explorer](https://learn.microsoft.com/en-us/fabric/data-engineering/navigate-lakehouse-explorer) in  fabric UI to upload files from your local machine to one lake directly. </br>

In many scenarios you might want to upload a local file and combine this with data coming in from other systems. These scenarios are enabled for you using Fabric. </br>

