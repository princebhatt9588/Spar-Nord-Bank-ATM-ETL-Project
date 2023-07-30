# Spar_Nord_Bank_Atm Project Overview

The main objective of this project is to build a batch Extract, Transform, Load (ETL) pipeline that reads transactional data from an RDS (Relational Database Service), performs necessary transformations, and loads the data into target dimensions and facts on Redshift Data Mart (Schema).

The dataset contains transactional data from over 100 ATMs across Denmark. Each transaction includes details such as card type, location, date, time, ATM type, etc. Additionally, a transaction amount field has been generated using a random function for analysis purposes.

Spar Nord Bank has already created a dimensional model datastore (ATM Data Mart) based on this transaction data to understand ATM usage patterns. The exact schema (target schema) of this Data Mart will be provided for this project. Redshift tables will be created according to this schema.

The project tasks can be summarized as follows:

1. **Data Extraction:** Extract transactional data from the given MySQL RDS server to an HDFS (EC2) instance using Sqoop.

2. **Data Transformation:** Transform the transactional data according to the provided target schema using PySpark.

3. **Data Loading:** Load the transformed data into an S3 bucket.

4. **Redshift Table Creation:** Create Redshift tables based on the provided schema.

5. **Data Loading to Redshift:** Load data from Amazon S3 into the newly created Redshift tables.

6. **Analysis Queries:** Perform various analytical queries to gain insights from the data:
   - Identify the top 10 ATMs with the most transactions in the 'inactive' state.
   - Determine the number of ATM failures corresponding to different weather conditions recorded at the time of transactions.
   - Find the top 10 ATMs with the highest number of transactions throughout the year.
   - Calculate the number of overall ATM transactions going inactive per month for each month.
   - Identify the top 10 ATMs with the highest total amount withdrawn throughout the year.
   - Analyze the number of failed ATM transactions across various card types.
   - Find the top 10 records with the number of transactions ordered by ATM_number, ATM_manufacturer, location, weekend_flag, and total_transaction_count, both on weekdays and weekends throughout the year.
   - Determine the most active day in each ATMs located in "Vejgaard".

The successful execution of this ETL pipeline and analytical queries will provide valuable insights into ATM usage patterns and help Spar Nord Bank make data-driven decisions.
