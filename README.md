# On-Premise-Database-Migration-with-Realtime-sync
#### Migrate an on-premise database to Azure SQL with real-time reports

## Getting Started

To get started with this project, you must have access to an on-premise StackOverflow SQL Server database by Brent Ozar and an Azure subscription. You will also need to have the following tools installed:

- Azure Data Factory
- Azure DataLake Gen 2
- Azure Key Vault
- Azure SQL Server Database
- Databricks
- Power BI

## Installation

1. Clone this repository to your local machine.
2. Create an Azure Data Factory instance and link it to your Azure subscription.
3. Create an Azure Key Vault instance and store your sensitive credentials.
4. Create a Databricks workspace and link it to your Azure subscription.
5. Create a Power BI account and link it to your Azure subscription.
6. Follow the instructions in the `README.md` file in each folder to set up the bronze, silver, and gold containers.

## Usage

Once you have set up the bronze, silver, and gold containers, you can use the following steps to migrate your data from the on-premise StackOverflow SQL Server database to Azure SQL and visualize it with Power BI:

1. Run the pipelines in Azure Data Factory to copy the data from the on-premise database to the bronze container in Azure Data Lake Gen 2.
2. Run the Databricks notebooks in the bronze folder to transform the data and load it into the silver container.
3. Run the Databricks notebooks in the silver folder to further transform the data and load it into the gold container.
4. Connect Power BI to the gold container to visualize the data.

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request.
