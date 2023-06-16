#  Loading Data At Scale
In the previous blog, we discussed what options Microsoft Fabric provides to load smaller files on an ad-hoc basis.  To ingest larger datasets, Fabric provides you with highly scalable options to load the dataset at great speeds. These could also be scheduled to run on a regular basis. For more advanced users, techniques like Metadata Driven copy will be discussed, which is a neat way to implement data loads at larger organizations having a large number of data objects. </br>

Microsoft Fabric offers [Data Factory](https://learn.microsoft.com/en-us/fabric/data-factory/), which is a SaaS offering for data loading, transforming data to the form understandable for business, and orchestration of the processes involved. Data Factory provides Data Flow Gen2 and Pipelines as two components. For users coming from a power bi background, you would be familiar with data flows that are used to transform data. Data Flow Gen2 is similar and provides low-code/citizen developer capabilities to prepare your data. Data Pipelines provides great data orchestration capabilities to load data into your storage layer. </br>

# Load Data - One Time

Fabric provides you capabilities in both Data Flow Gen2 as well as Data Pipelines to load your data. For relatively smaller files, Data Flow Gen2 provides you with the GetData option to fetch data from a multitude of sources. This contains 150+ connectors to different sources you can connect to get your data. Using Data Flow Gen2 you can also load data from the OneLake storage. The option to upload a file from the local machine, using drag and drop is also available.

![load_options_dfg2](/images/connect_options_dfg2.png)

Pipelines provide a scalable option to pull in large datasets using [copy activity](https://learn.microsoft.com/en-us/fabric/data-factory/copy-data-activity). Fabric provides you with a copy assistant which helps to easily connect to a source where the data is residing and then copy it to the storage, which is OneLake. 

![load_data](/images/copy_assistant.png)

# Load Data - Scheduled 

With Data Factory Data Pipelines, fabric provides you with a scalable and easy-to-use orchestration engine. Due to its SaaS nature, the engine decides how many resources to use providing you the necessary speed to load data. Data Pipelines  provide options for re-use by having parameters that help to create dynamic pipelines. Want to use pre-built pipelines for loading data, Fabric provides you with [templates](https://learn.microsoft.com/en-us/fabric/data-factory/templates) that can be leveraged. These templates cover common scenarios which are used to load data from different sources.
