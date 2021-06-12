## Table of contents
* [General Info](#general-info)
* [Description](#description)
* [Learning-Objectives](#Learning-Objectives)
* [Prerequisites](#Prerequisites)
* [Technologies](#technologies)
* [Setup](#setup)


## General Info
Guided Capstone project

## Architecture
![Alt text](Screenshot/architecture.PNG?raw=true "Architecture")

For a data processing system, the first step is to ingest the data sources. Your Spring Capital data sources come from stock exchange daily submissions files in a semi-structured text format. This means the records follow a certain formatting convention like JSON, but don’t obey a tabular structure formatted for a relational database. The data ingestion process parses the semi-structured data out so it can be loaded into Spark.

## Learning-Objectives
* Learn to parse CSV and JSON files
* Create a Spark DataFrame with defined schema
* Persist the Spark DataFrame into file system using partitioning


## Prerequisites
* Python: basics, string manipulation, control flow, exception handling, JSON parsing
* PySpark: RDD from text file, custom DataFrames, write with partitions, Parquet


## Technologies
Project is created in Azure Portal using the following services:
* Azure Storage Container
* Azure Databricks


## Setup

Follow the steps highlighted below. Check the  document Guided Capstone Project.docx for complete steps.

* Create a Storage Account and a container under the storage account in Azure
* Assign role in Storage Account's Access Control
* AzCopy commands to move data from local to Storage Account

```
azcopy copy "C:/SpringBoard-DE-Projects/Step 2 - Data Ingestion/data/" "https://ingestresourcegrp.blob.core.windows.net/springcapital" --recursive=true

```
* Open the azure databricks notebook , create cluster and and follow the commands in sequence from az-databricks-blob, parse_csv, parse_json python files. check the  document Guided Capstone Project.docx for complete project steps.
```
storageAccountName = '<storageAccountName>'
storageAccountAccessKey = '<storageAccountAccessKey>'
blobContainerName = '<blobContainerName>'

```

The detailed steps and screenshots are in the document 'Guided Capstone Project.docx'


* CSV Records before parsing

![Alt text](Screenshot/raw_csv_records.PNG?raw=true "CSVBeforeParse")

* CSV Records after parsing

![Alt text](Screenshot/parsed-CSV.PNG?raw=true "CSVAfterParse")

* JSON Records before parsing

![Alt text](Screenshot/raw_json_records.PNG?raw=true "JSONBeforeParse")

* JSON Records after parsing

![Alt text](Screenshot/parsed-json.PNG?raw=true "JSONAfterParse")
