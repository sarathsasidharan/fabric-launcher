#  Loading Data At Scale
Previous blog we discussed what options Microsoft Fabric provides to load smaller files on an ad-hoc basis. This one we focus on what are the options avaiable to load larger datasets into Fabric. First section we will focus on how to do this one off , by connecting to the data source and pulling this data into Fabric , followed by scheduling the data load at a regular interval. For more advanced users , later we will cover techniques like Metadata Driven copy which is a neat way to implement data loads at larger organizations which have a large number of data objects which need to be brought in. </br>

Microsoft Fabric offers [Data Factory](https://learn.microsoft.com/en-us/fabric/data-factory/) , which is a SaaS offering for data loading , transforming data to the form understandable for business and orchestration of the processes involved. Data Factory provides Data Flow Gen2 and Pipelines as two compoenents within it. For users coming from a power bi background , you would be familiar with data flows which is used to transform data. Data Flow Gen2 is similar and provides low-code/citizen developer capabilites to prepare your data. Data Pipelines provides great data orchestration capabilities to load data into your storage layer. </br>

# Load Data - Manual

Fabric provides you capabilites in both Data Flow Gen2 as well as Data Pipelines to load your data. 
