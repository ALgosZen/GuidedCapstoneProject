## Table of contents
* [General Info](#general-info)
* [Description](#description)
* [Technologies](#technologies)
* [Setup](#setup)


## General Info
This project is Data Ingestion step of Guided Capstone project

## Description
Spring Capital data sources come from stock exchange daily submissions files in a semi-structured text format. This means the records follow a certain formatting convention like JSON, but don’t obey a tabular structure formatted for a relational database. The data ingestion process parses the semi-structured data out so it can be loaded into Spark

The data that’s submitted by exchanges will be in two different formats: CSV and JSON. CSV means Comma Separated Values, so it is a text document that contains many values separated by commas. JSON is JavaScript Object Notation, in which text data is stored following a standard convention. Both of these are flat text files containing trade and quotes from different numbers of fields. The record type can be identified by column ‘rec_type’ which is a fixed position for CSV files.


## Technologies
Project is created in Azure Portal using the following services:
* Azure Storage Container
* Azure Databricks


## Setup

Follow the steps highlighted below. Check the word document for complete steps.

* Create a Storage Account and a container under the storage account in Azure
* Assign role in Storage Account's Access Control
* AzCopy commands to move data from local to Storage Account

```
azcopy copy "C:/SpringBoard-DE-Projects/Step 2 - Data Ingestion/data/" "https://ingestresourcegrp.blob.core.windows.net/springcapital" --recursive=true

```
* Open the azure databricks notebook and following the commands as shown in az-databricks-blob, parse_csv, parse_json python files. check the word document for complete steps.
```
storageAccountName = '<storageAccountName>'
storageAccountAccessKey = '<storageAccountAccessKey>'
blobContainerName = '<blobContainerName>'

```

* Create a Databricks cluster and notebook and run the code in files 'databricks.py','parse_csv.py' and 'parse_json.py'

The detailed steps and screenshots are in the document 'Guided Capstone Data Ingestion.docx'


* CSV Records before parsing

![Alt text](Screenshot/raw_csv_records.PNG?raw=true "CSVBeforeParse")

* CSV Records after parsing

![Alt text](Screenshot/parsed_csv_records.PNG?raw=true "CSVAfterParse")

* JSON Records before parsing

![Alt text](Screenshot/raw_json_records.PNG?raw=true "JSONBeforeParse")

* JSON Records after parsing

![Alt text](Screenshot/parsed_json_records.PNG?raw=true "JSONAfterParse")
