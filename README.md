# Amazon Vine Analysis

## Overview of the Analysis

### Purpose

The purpose of this project is to analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. 

### Approach

In this project, the Amazon Vine dataset with reviews of **Electronics** products has been used. With PySpark, the ETL process is performed to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Then the PySpark was used to determine if there is any bias toward favorable reviews from Vine members in the dataset. 

### Deliverables: 

1. Perform ETL on Amazon Product Reviews
2. Determine Bias of Vine Reviews
3. A Written Report on the Analysis 

### Tools and Data Sources

#### Tools

- PySpark
- Python Scripts
- PostgreSQL
- Google Colaboratory
- AWS RDS (Aurora)
- AWS S3

#### Data Sources

- [Amazon Review Datasets](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt)

### ETL Process

#### Setting Up an AWS DRS Database

![RDS DB](/Resources/aws_rds_db.png)

#### Connecting to pgAdmin & setting up a Schema

![Connection](/Resources/aws_server_connection_from_pgadmin.png)

#### Extract & Transform in PySpark

**Customers DataFrame**
![Customers_DF](/Resources/c_df_e.png)

**Products DataFrame**
![Products_DF](/Resources/p_df.png)

**Review Id DataFrame**
![Review_Id_DF](/Resources/r_df.png)

**Vine DataFrame**
![Vine_DF](/Resources/v_df.png)

#### Load the Data to PostgreSQL

**Customers Table**
![Customers_Table](/Resources/customers_table.png)

**Products Table**
![Products_Table](/Resources/products_table.png)

**Review Id Table**
![Review_Id_Table](/Resources/review_id_table.png)

**Vine Table**
![Vine_Table](/Resources/vine_table.png)

## Results

### How many Vine reviews and non-Vine reviews were there?

### How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

### What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

## Summary

## T-Tests on Suspension Coils

**Problem 1**: Determine if the PSI across all manufacturing lots is statistically different from the population mean of 1,500 pounds per square inch

**Solution 1**: Based on the **0.05 significance level**, there is **no statistical difference** of the aggregated manufacturing lots sample from the population mean: 

- the p-value = 0.06.

The aggregated t-test summary is presented below:

![Total Summary](/Resources/Total_T.test.png)