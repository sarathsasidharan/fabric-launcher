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

The third option for users familiar with azure , there is also support for [Azure Storage Explorer](https://learn.microsoft.com/en-us/fabric/onelake/onelake-azure-storage-explorer).This provides you the ability to connect to a Lakehouse item and view / download / upload files or folders. 

Once the data is uploaded , whats next. We need to work with the data.  If you are from the SQL world , Fabric gives you a super fast option to start querying the data you have loaded. Right click the file loaded and select load to table option. That's it without having to create table explicilty Fabric does the plumbing to create the table for you.


![load_to_table](/images/load_to_table.png)

From here you Fabric provides you an option to query the data using your SQL Skills. Switch to the SQL endpoint view by clicking on the top right corner.

![sql_endpoint](/images/sql_endpoint.png)

After the switch you would need to select the New SQL Query Option at the top and start with analysing your data using sql. There is also a [visiual query builder](https://learn.microsoft.com/en-us/fabric/data-warehouse/visual-query-editor) feature for users who are new to SQL but come from a PBI data flow background to help you build queries.

![sql_query](/images/sql_query.png)

Even further if you are a PBI /BI dev and would prefer power bi , then this data also gets added to a powerbi dataset for you to analyze without any work from your end. You could click on the Model tab at the bottom and this should allow you start working with your data in power bi. More on this in a later blog. For now , the first step to get the data into the platform is done and options to quickly get it to work for your needs is enabled by fabric.

![power_bi](/images/power_bi.png)

This blog we have focussed on ad-hoc / quick ways to upload your data into fabric. Next up we will cover how would you load data at scale and what fabric offers in that space. Stay Tuned !
