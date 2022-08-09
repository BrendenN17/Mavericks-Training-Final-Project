# Mavericks-Training-Final-Project

This repo contains all of my files related to my final project (8/9)

Includes many screenshots as well as the Notebook file and the resulting output parquet file


## The steps I followed for this project were:
1. Create AWS s3 bucket 'hackathon-bucket-17'
2. Upload 'covid_19.csv' to my s3 bucket 
3. Create Database in AWS Glue 'hackathon-db'
4. Created a crawler 'hackathon-crawler' inside of 'hackathon-db' to crawl data from my s3 bucket
5. Created an IAM user 'gluerole' which I give full s3 permissions and full aws glue permissions
6. Next I opened the AWS Glue studio and created a new job 
7. The job source has the Data Catalogue source type with a db 'hackathon-db' and a table 'covid_19.csv'
8. I added an aggregate transformation in the interactive glue studio environment which groups the data once by 'country/region' and again by 'province/state'. The aggregation performed for the grouped data is max cases, max deaths, and max recoveries for both groups.
9. Finally I choose a target for my results of the transformation to be saved. In this case, the target is the s3 bucket i created 'hackathon-bucket-17' and the type is a parquet file.
10. I fill in the job details with the name 'hackathon-job' and assign the IAM user i created previously to this job
11. I then save the job and run it. 
12. After checking job details and seeing it run successfully, I checked and made sure that parquet output files existed in my s3 bucket.
13. I download one of these parquet files in order to examine the contents. 
14. In a jupyter notebook, I import pyarrow.parquet as pq ( a library which allows us to work with parquet files)
15. I then open this parquet file inside of my jupyter notebook and convert to a pandas table to view the contents and ensure they are as expected.
