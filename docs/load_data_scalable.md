#  Loading Data At Scale
In the previous blog, we discussed what options Microsoft Fabric provides to load smaller files on an ad-hoc basis.  To ingest larger datasets, Fabric provides you with highly scalable options to load dataset at great speeds. These could also be scheduled to run on a regular basis. For more advanced users, techniques like Metadata Driven copy will be discussed, which is a neat way to implement data loads at larger organizations having a large number of data objects. </br>

Microsoft Fabric offers [Data Factory](https://learn.microsoft.com/en-us/fabric/data-factory/), which is a SaaS offering for data loading, transforming data to the form understandable for business, and orchestration of the processes involved. Data Factory provides Dataflows Gen2 and Pipelines as two components. For users coming from a power bi background, you would be familiar with dataflows that are used to transform data. Dataflows Gen2 is similar and provides low-code/citizen developer capabilities to prepare your data. Data Pipelines provides great data orchestration capabilities to load data into your storage layer. </br>

# Load Data - One Time

Fabric provides you capabilities in both Dataflows Gen2 as well as Data Pipelines to load your data. For relatively smaller files, Dataflows Gen2 provides you with the GetData option to fetch data from a multitude of sources. This contains 150+ connectors to different sources you can connect to get your data. Using Dataflows Gen2 you can also load data from the OneLake storage. The option to upload a file from the local machine, using drag and drop is also available.

![load_options_dfg2](/images/connect_options_dfg2.png)

Pipelines provide a scalable option to pull in large datasets using [copy activity](https://learn.microsoft.com/en-us/fabric/data-factory/copy-data-activity). Fabric provides you with a copy assistant which helps to easily connect to a source where the data is residing and then copy it to the storage, which is OneLake. 

![load_data](/images/copy_assistant.png)

# Load Data - Scheduled 

With Data Factory Data Pipelines, fabric provides you with a scalable and easy-to-use orchestration engine. Due to its SaaS nature, the engine decides how many resources to use providing you the necessary speed to load data. Data Pipelines  provide options for re-use by having parameters that help to create dynamic pipelines. Want to use pre-built pipelines for loading data, Fabric provides you with [templates](https://learn.microsoft.com/en-us/fabric/data-factory/templates) that can be leveraged. These templates cover common scenarios which are used to load data from different sources.

## Metadata Driven Load 
In any organization, you will have a lot of data sources and tables/files within these sources which need to be imported to your storage. Creating a single pipeline per table/file is a nightmare to manage and duplication of work. Data Pipelines provides you the option to get rid of this. By parameterizing these table/file names you no longer have to create hundreds of pipelines. Using [Lookup activity](https://learn.microsoft.com/en-us/fabric/data-factory/lookup-activity) you can create a configuration file/table in a database where you could define the metadata of these objects. Sharing an example of my config table where the details for tables to be copied are provided.

![config](/images/config_table.png)

Lookup activity reads this configuration table.

![pipeline](/images/meta_pipe.png)

It's easy to set up the Lookup activity, it just needs to point to the configuration table on the database.

![lookup](/images/lookup.png)

 Next up this list of tables retrieved from the table have to be copied into the storage. Pipelines provide you with a control flow activity, which is the [ForEach](https://learn.microsoft.com/en-us/fabric/data-factory/foreach-activity) activity. This allows us to iterate through the list of tables retrieved from the configuration table and copies it into the storage.

In order to retrieve the values from the lookup activity, pipelines provide you with the magical activity output which helps you with this. This is super easy since when the item's text box is selected the dynamic content builder will help with getting the right parameter values. 

![for-loop](/images/for-loop.png)

Insider the ForEach Activity, the copy activity is added which accepts the table name as a parameter and executes the copy. The parameterization for the source is represented below.
![source-table](/images/source-table.png)

Similar to the source the sink needs to be parameterized too, also do note that the sink is into the lakehouse.  This is going to automatically create a table inside the lakehouse.
![sink-table](/images/sink-table.png)

In this case, it's copying it to a [lakehouse](https://learn.microsoft.com/en-us/fabric/data-engineering/lakehouse-overview). This is immediately available to query using T-SQL.

![lake-house](/images/lake-house.png)

## Scheduling

Pipelines are ready and kicking, the next part is to automate this. Fabric via Data Pipelines provides you with [scheduling](https://learn.microsoft.com/en-us/fabric/data-factory/pipeline-runs#scheduled-data-pipeline-runs) capabilities to trigger these pipelines. This helps to run this data load operation at regular intervals based on how your data arrives. Scheduling is available up to a minute interval. For PBI users, these pipelines can also trigger data flow gen2 .

## Notifications

Last but not least, Fabric Data Pipelines provides you the [Outlook activity](https://learn.microsoft.com/en-us/fabric/data-factory/tutorial-end-to-end-integration#add-an-office-365-outlook-activity-to-your-pipeline), which is a super cool feature to send mail notification. This is a great feature to notify the status of important /business critical jobs as they are completed.

Microsoft Fabric is intended to make things easier and quicker for you and your organization to achieve more from data, in case you have ideas that could make this even better, please post your ideas to: https://ideas.fabric.microsoft.com/ , you could search if it has been already requested and upvote for your features to get into our dev list.



