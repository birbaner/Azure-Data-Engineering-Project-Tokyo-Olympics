# Azure-Data-Engineering-Project-Tokyo-Olympics 

The Tokyo Olympic Data Analysis on Azure project demonstrates an end-to-end data engineering and analytics solution for exploring Olympic Games data using Azure's cloud services. Starting with a CSV dataset hosted on GitHub, the data is ingested into Azure through Azure Data Factory and stored in Azure Data Lake Storage Gen2. It is then transformed and enriched using Azure Databricks before undergoing advanced analytics in Azure Synapse. The final insights are visualized using Azure Synapse or Power BI, showcasing a scalable and efficient approach to processing, transforming, and analyzing large volumes of data while leveraging the power of Azure's ecosystem.

![Azure Data Engineering Project](https://github.com/birbaner/Azure-Data-Engineering-Project-Tokyo-Olympics/blob/9f34e518a4e38b329cd46b2a6127db981798c68c/Azure.png?raw=true)

## Dataset Used 
This contains the details of over 11,000 athletes, with 47 disciplines, along with 743 Teams taking part in the 2021(2020) Tokyo Olympics.
This dataset contains the details of the Athletes, Coaches, Teams participating as well as the Entries by gender. It contains their names, countries represented, discipline, gender of competitors, name of the coaches.

Source(Kaggle): [2021 Olympics in Tokyo](https://www.kaggle.com/datasets/arjunprasadsarkhel/2021-olympics-in-tokyo)

## Azure Services Used
1. **Azure Data Factory:**  Used as the data ingestion tool to connect to the CSV dataset hosted on GitHub, enabling automated and scheduled data pipelines for seamless data import into the Azure ecosystem.
2. **Azure Data Lake Storage Gen2**: Serves as the primary data storage solution, providing a scalable and secure environment for storing raw and transformed data, ensuring high availability and efficient data management.
3. **Azure Databricks:** Utilized for data transformation and enrichment tasks, leveraging its powerful Spark-based analytics engine to clean, preprocess, and transform the data into a structured format suitable for advanced analytics.
4. **Azure Synapse Analytics:** Enables in-depth data analytics by processing the transformed data, running complex queries, and creating aggregated datasets for generating insights and supporting visualization dashboards.

   
## Workflow 

## Initial Setup
1.  Create Azure Free Subscription Account: Sign up for a free Azure subscription to access Azure services.  
2. Create a Resource Group: Set up a resource group named tokyo-olympic-data to manage all resources associated with this project.
3. Set Up Storage Account: Create a storage account within the resource group, configured specifically to use Azure Data Lake Storage (ADLS) Gen2 for efficient data management.
4. Create Data Container and Directories: Inside the storage account, create a container to hold project data. Add two directories:
            raw-data for storing the raw ingested data.
            transformed-data for saving data after transformations.
     
# Data Ingestion Using Azure Data Factory
1.Create Azure Data Factory Workspace: Set up a Data Factory workspace within the resource group.

2.Launch Data Factory Studio: Open Azure Data Factory Studio to design and manage data pipelines.

3.Prepare Dataset: Upload the Tokyo Olympics dataset from Kaggle to GitHub for easy access via HTTP.

4.Create Data Integration Pipeline:
     Initialize a new pipeline in Azure Data Factory Studio.
     Use the Copy Data activity to efficiently move data between the GitHub source and ADLS Gen2 destination.
     
5.Configure Data Source and Sink:
      Set up the data source using the HTTP template to pull data from the GitHub repository.
      Establish a linked service for both the source and sink.
      Configure the file format for the ingested data.
      
6.Run Data Pipelines: Repeat the above steps for all datasets (e.g., athletes.csv, medals.csv). Connect all Copy Data activities and execute them simultaneously.

7.Validate Data: After the pipeline execution, navigate to the raw-data folder in ADLS Gen2 and verify the presence of datasets.

# Data Transformation Using Azure Databricks
1.Set Up Azure Databricks Workspace: Create a Databricks workspace within the resource group and launch it.

2.Configure Compute Resources: Set up a cluster in Databricks to handle data processing tasks.

3.Create a Notebook:
Create and rename a new Databricks notebook to reflect its purpose (e.g., "Data Transformation").
     
4.Connect Databricks to ADLS Gen2:
  Use credentials such as Client ID, Tenant ID, and Secret to write code in the notebook for mounting ADLS Gen2 to Databricks.
     
5.Perform Data Transformation:
    Clean, preprocess, and transform the data as required.
    Save the transformed data back into the transformed-data directory in ADLS Gen2.

6.Refer to the Transformation Notebook: Refer to Tokyo Olympics Transformation.ipynb for the transformation code and steps.

# Data Analysis Using Azure Synapse Analytics

1.Set Up Synapse Workspace: Create a Synapse Analytics workspace within the resource group.

2.Create Lake Database: Navigate to the "Data" section, select "Lake Database," and create a new database named TokyoOlympicDB.

3.Create Tables from Transformed Data: Use the transformed data stored in ADLS Gen2 to define tables in the database.

4.Perform Data Analysis:

    Write and execute SQL scripts to perform exploratory data analysis (EDA) on the ingested datasets.
    Identify patterns, trends, and insights from the data.
    
5.Visualize Data: Use Power BI to create detailed and interactive dashboards for further analysis and visualization. 

 
