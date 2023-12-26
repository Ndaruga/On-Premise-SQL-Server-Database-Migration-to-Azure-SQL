# On-Premise SQL Server Database Migration to Azure SQL
#### Migrating StackOverflow Database to Azure SQL, Power BI Reporting, and Secure Integration with Azure Services
![image](https://github.com/Ndarugaa/On-Premise-Database-Migration-with-Realtime-sync/assets/68260816/8833acc1-426a-41a0-b052-95934996237b)

>This repository contains a data engineering project that migrates data from an on-premise StackOverflow SQL Server database by Brent Ozar to Azure SQL and visualizes it with Power BI for reporting. The project uses a self-hosted integration runtime to connect the data from on-premise to Azure Data Lake Gen 2 using Azure Data Factory. Sensitive credentials are stored in Azure Key Vault, and transformations are done in three steps with Databricks.
## Getting Started

To get started with this project, you must have access to: 
 - An on-premise SQL Server database.
 - An <a href="https://azure.microsoft.com/en-us/free" target="_blank">Azure subscription</a>.
 - <a href="https://www.microsoft.com/en-us/download/details.aspx?id=58494" target="_blank">Power BI</a> For Windows PC.

### Quick Start to set up an on-premise SQL server Database
To set up an on-premise SQL Server database, you can follow the general steps outlined below to install it on your local PC.
> - To have a quick on-premise SQL server database, <a href="https://www.microsoft.com/en-us/sql-server/sql-server-downloads" target="_blank">Download and install</a> the free `Developer` Edition of SQL Server.
> - Proceed to install an SQL Server Management tool like <a href="https://go.microsoft.com/fwlink/p/?linkid=2206714">SSMS</a> or <a href="https://go.microsoft.com/fwlink/p/?linkid=2206560" target="_blank">Azure Data Studio</a>.
> - Establish the connection between the Management tool and the SQL-Server database by creating  a `New connection`.
> - In this project, I have used the <a href="https://www.brentozar.com/archive/2015/10/how-to-download-the-stack-overflow-database-via-bittorrent/">StackOverflow Database</a> by Brent Ozar.
>    - Download and Extract the Zip files.
> - Open the Management tool you previously installed. On the `Database` tab or option select `attach Database` and select the `Microsoft Database File (.MDF)` file.
> - Your on-premise database should be up and running.
It's important to note that the specific steps for setting up an on-premise SQL Server database may vary based on your environment and requirements. Always refer to the official documentation and best practices for the most accurate guidance.


You will also need to have the following resources in your Azure Subscription created:
- Resource Group
- Azure Data Factory
- Azure DataLake Gen 2
- Azure Key Vault
- Azure SQL Server Database Instance
- Azure Databricks
  > Please ensure you deploy your resources within the same region where applicable


## Installation

1. Clone this repository to your local machine.
2. Create an Azure Data Factory instance in your Azure subscription.
3. Create an Azure datalake gen 2 to store data during transformations.
4. Create an Azure Key Vault instance and store your sensitive credentials.
5. Create a Databricks workspace and link it to your Azure Data Factory
6. Link Power BI to the Azure SQL Server Database


## Usage

Once you have set up the bronze, silver, and gold containers in the Datalake, you can use the following steps to migrate your data from the on-premise StackOverflow SQL Server database to Azure SQL and visualize it with Power BI:

1. Run the pipelines in Azure Data Factory to copy the data from the on-premise database to the bronze container in Azure Data Lake Gen 2.
2. Run the Databricks notebook `bronze-to-silver` to transform the data in the bronze container and load it into the silver container.
3. Run the Databricks notebook `silver-to-gold` to transform the data in the silver container and load it into the gold container.
4. Run the Databricks notebook `gold-to-SQL` to load the transformed data from the gold container to the Azure SQL Database.
4. Connect Power BI to the Azure SQL Database to visualize the data.

## Trigger
Once the pipeline has run successfully, configure a trigger to run the pipeline at a specified time of your choice.

For Instance, You could configure the trigger to execute the pipeline at exactly 00:00 or 16:00 every day 

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request.
