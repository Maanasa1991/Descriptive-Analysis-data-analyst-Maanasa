**DESCRIPTIVE ANALYSIS**

**Project Description:** Descriptive Analysis of Building permits for the City of Vancouver

**Project Title:** Creating a DAP Design and Implementation 

Objective: The primary goal of this project is to conduct a descriptive analysis of building permits data for the City of Vancouver. Through this analysis, we aim to summarize key characteristics of permit number, permit elapsed days, project value to identify trends, and generate insights that can inform Vancouver authorities who are giving permissions to build houses or other buildings based on the location, permit category and there are more things to consider.

**Dataset: **

My dataset consists of following data includes

o	Permit Number: Unique identifier for each applicant

o	Permit Number Created Date: When the permit number has created

o	Permit Elapsed Days: Within how many days the permits are going to be elapsed

o	Project Value: The value of the building

o	Permit Category: Renovation - Renovation/ Demolition/ completed

o	Geo Local Area - The location of the building

**Methodology:**

1-	Data Collection and Preparation:

Downloaded the dataset from the below link:

https://opendata.vancouver.ca/explore/dataset/issued-building-permits/information/?refine.issuedate=2024&refine.geolocalarea=Kensington-Cedar+Cottage&refine.specificusecategory=Single+Detached+House&dataChart=eyJxdWVyaWVzIjpbeyJjaGFydHMiOlt7InR5cGUiOiJsaW

<img width="451" alt="image" src="https://github.com/user-attachments/assets/297fbfa2-6fe5-44d7-8c28-d84182ea2ce7">

The chart above shows permit processing times for single detached houses in Kensington-Cedar Cottage for the year 2024. Each of the bars shows the count of permits processed within particular time ranges by their creation dates. This visualization helps to identify patterns and potential delays in the permit issuance process for effective analysis.

Design the DAP by using draw.io

<img width="451" alt="image" src="https://github.com/user-attachments/assets/115fe918-5482-4a1c-8c8e-cd4ff1bf0cd6">

It explains a Data Analytic Platform using AWS services for the City of Vancouver. Initially, raw dataset is stored in Amazon S3 bucket(van-bp-raw-maan), By using AWS data brew services I did the profiling by creating project and then cleaning job by using filter functions creating a job by using the profiled dataset. We can check and change by using recipe option. Once it is done, by using Data Glue service I created a visual ETL for pipeline design. At the end the desired will, be stored in S3 transformed bucket(van-bp-tra-maan).

1.	Data Ingestion:

   <img width="451" alt="image" src="https://github.com/user-attachments/assets/486974e9-3261-472c-834a-203d70ac1548">

   Lifecycle Configuration:

   <img width="451" alt="image" src="https://github.com/user-attachments/assets/c7caba76-7eee-40fe-880d-035c235ac4f6">

   In Data ingestion, created buckets according to the domain I have chosen for City of Vancouver. In raw bucket I inserted the raw dataset (Excel file). While inserting the dataset based on my requirement, I selected Standard storage class which will be appropriate for my platform.

   2.	Data Profiling

<img width="451" alt="image" src="https://github.com/user-attachments/assets/4c1eb97a-f238-4b61-92a7-c39304c93b22">

In Data Profiling step, used the AWS Data Brew service to profile the raw data. It mainly involves assessing the dataset quality by identifying any missing values, duplicate values. By using Data profile view we can do the profiling by using column statistics checked the columns which are accurate for my further work. The output of the file is in json format.

3.	Data Cleaning

<img width="451" alt="image" src="https://github.com/user-attachments/assets/dda6c608-0dc0-4e37-b0d0-461ea1a945f8">

Data cleaning result in User:

<img width="451" alt="image" src="https://github.com/user-attachments/assets/8b2da91a-d1aa-4ad9-b88d-e602add07920">

Data cleaning result in System:

<img width="452" alt="image" src="https://github.com/user-attachments/assets/595ac4de-83bc-45b6-a81d-51d00c396512">

In Data cleaning, first step is to create separate folders for User and System in S3 under Transform bucket. Once profiling is done, by using that data created one project and, in that project, prepared some recipes to clean the dataset. After applying the recipes, now the dataset is accurate, reliable and free of errors. The cleaned data sets are stored back in S3.!

4.	Pipeline Design

<img width="452" alt="image" src="https://github.com/user-attachments/assets/f8ad7984-45ca-4c1e-9f6c-0efe76b11672">

Pipeline Result in S3 (system)

<img width="452" alt="image" src="https://github.com/user-attachments/assets/9245511a-efec-4275-90cf-06f3bb1fd479">

Pipeline Result in S3 (user)

<img width="452" alt="image" src="https://github.com/user-attachments/assets/b65cca2e-211d-4348-a2de-aad1afcf0863">

In pipeline design, I used Data Glue service to create a ETL diagram by connecting all the steps. I used Amazon S3, Change Schema, Aggregate, Filter function and at the end Used S3 again to store the output. I applied the formula by using the pipeline. This is an effective way to find reliable answers for our questions to datasets. It is visual, so it is more effective.

Conclusion:

o	Received desired results of an average number of building permits by using pipeline design and Athena. Stored the final results in S3.

Tools and Technologies:

o	Draw.io - AWS - S3 - AWS Glue - AWS Brew - AWS Athena

This descriptive analysis project aims to provide a comprehensive understanding of distributing and approving building permits, enabling The City of Vancouver to optimize its operations and enhance the results of applicants satisfaction.




























# Descriptive-Analysis-data-analyst-Maanasa
