---
title: Getting Started with Autoloader
domain: factorsense.nl 
tags: databricks, azure
subtitle: Incremental processing of new data as they arrive in cloud storage without any additional setup.
slug: 
cover: 
publishAs: 
canonical:
---
One of the most common use cases we have had in the ETL workloads is the incremental processing of the new data coming in from the sources. During early days of career when I was part of a production support team, I still remember we had this File Watcher component in our framework which used to keep watching for the files in the landing folder. The file watcher used to register each file coming into the landing layer and once all the required conditions were met the component used to process all the data into the Datawarehouse.



Fast forward 2022, we are in this amazing world of object based storage, like S3, ADLS, Azure Blobs, in the cloud which are often used for storing the data extracted from the source systems. Now we all know that the object based storage are not one of the best when it comes to directory listing. Repeatedly listing the cloud directory and tracking the files is a slow and a costly process and gets worse as the directory keeps growing. 
Some of the options we have implemented in the past is either loading the data in batches or having some sort of notification service to notify arrival of files and trigger the load process. Well to be honest, there is nothing wrong in either of the way. The first one, where you load batches in a schedule, increases the turn around time between landing of data and availability of data for consumption in reports. Second one can add up to the cost and maintenance of your data platform. And lets agree, both the options are too boring in 2022.