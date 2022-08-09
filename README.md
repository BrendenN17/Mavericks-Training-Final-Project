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
8. 
