# Web application development with ASP.NET Core MVC using Azure Cosmos DB

This sample shows you how to use the Microsoft Azure Cosmos DB service to store and access data from an ASP.NET Core MVC application hosted on Azure App Service

## Configuration

The application requires a connection string and a secret:

- **DB_URL**: URL of the cosmosDB endpoint
- **DB_SECRET**: key to connect to the database

Application can also read from ENV variables: (__is a double underscore for containers. standard applications can use ":" instead)

- **COSMOSDB__DB_URL**: URL of the cosmosDB endpoint
- **COSMOSDB__DB_SECRET**: key to connect to the database

## Running this sample in Visual Studio

1. Before you can run this sample, you must have the following perquisites:
    - Visual Studio 2017 (or higher).
    - An active Azure Cosmos account or the [Azure Cosmos DB Emulator](https://docs.microsoft.com/azure/cosmos-db/local-emulator) - If you don't have an account, refer to the [Create a database account](https://docs.microsoft.com/en-us/azure/cosmos-db/create-sql-api-dotnet#create-an-azure-cosmos-db-account) article

2.Clone this repository using Git for Windows (http://www.git-scm.com/), or download the zip file.

3.From Visual Studio, open the [CosmosWebSample.csproj](./src/CosmosWebSample.csproj).

4.In Visual Studio Build menu, select **Build Solution** (or Press F6). 

5.Retrieve the URI and PRIMARY KEY (or SECONDARY KEY) values from the Keys blade of your Azure Cosmos account in the Azure portal. For more information on obtaining endpoint & keys for your Azure Cosmos account refer to [View, copy, and regenerate access keys and passwords](https://docs.microsoft.com/azure/cosmos-db/secure-access-to-data#master-keys)  **if you are going to work with a real Azure Cosmos account**.
    * The default configuration is setup to work with a local Azure Cosmos DB Emulator.

6.In the [appSettings.json](./src/appSettings.json) file, located in the project root, find **Account** and **Key** and replace the placeholder values with the values obtained for your account if you are going to work with a real Azure Cosmos account.

7.You can now run and debug the application locally by pressing **F5** in Visual Studio.

## Infrastructure as code

The folder **/deploy** contains the ARM template to provision a cosmosDB

## Kubernetes deployment

The folder **/manifest** contains the YAML manifest to deploy the application. Container image endpoint must be modified with your own value

## More information

- [Azure Cosmos DB Documentation](https://docs.microsoft.com/azure/cosmos-db)
- [Azure Cosmos DB .NET SDK](https://docs.microsoft.com/azure/cosmos-db/sql-api-sdk-dotnet)
- [Azure Cosmos DB .NET SDK Reference Documentation](https://docs.microsoft.com/dotnet/api/overview/azure/cosmosdb?view=azure-dotnet)
