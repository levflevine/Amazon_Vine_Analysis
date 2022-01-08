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

Customers DataFrame

![Customers_DF](/Resources/c_df.png)

Products DataFrame

![Products_DF](/Resources/p_df.png)

Review Id DataFrame

![Review_Id_DF](/Resources/r_df.png)

Vine DataFrame

![Vine_DF](/Resources/v_df.png)

#### Load the Data to PostgreSQL

Customers Table

![Customers_Table](/Resources/customers_table.png)

Products Table

![Products_Table](/Resources/products_table.png)

Review Id Table

![Review_Id_Table](/Resources/review_id_table.png)

Vine Table

![Vine_Table](/Resources/vine_table.png)

## Results

### Questions

- How many Vine reviews and non-Vine reviews were there? 
- How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars? 
- What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

### Answers

![Results](/Resources/vine_reviews_5_star.png)

## Summary

### Is there any positivity bias for reviews in the Vine program

Summary Statistics for the non-Vine reviews with a 5-Star Rating

![Free_Summary Stats](/Resources/free_summary_stats.png)

Summary Statistics for the Vine-participating reviews with a 5-Star Rating

![Paid_Summary_Stats](/Resources/paid_summary_stats.png)

**Initial Conclusion**. There is some level of positivity bias for the reviews in the Vine Program:  the mean of the ratings from the people participating in the Vine Program is 4.09/5.00 versus the mean of the ratings from the people, who dont' participate in the Vine program: 3.65/5.00. People in the Vine program, who are getting paid for providign the reviews, tend to provide better ratings. This initial conclusion needs to be statistically validated.

### One additional analysis with the dataset to support the conclusion

To validate the conclusion above, we need to perform a two-sample T-Test that will help to determine is the ratings for people in and out of the Vine program are statistically different. 

![T-Test Summary](/Resources/2-sample-t-test.png)

**Conclusion**: Based on the **0.05 significance level**, there is **no statistical difference** of the review ratings mean for the people in the Vine program and the review ratings mean for the people not enrolled the Vine program: 

- **the p-value = 1.78e-20, which is below our significance level**.

**Hence, there there is no statistically significant positivity bias for the reviews in the Vine Program.**

