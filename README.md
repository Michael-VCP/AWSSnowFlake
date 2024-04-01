# AWSSnowFlake

1. Search DynamoDB > Create table > Create table name as api name
2. Partiotion key (Partition key + Sort key = Primary key) > City and Time > Default settings > Create table
3. Search Lambda > Create function > Enter name > Python 3.10 > Create function > Test function, Invoke function, and modify code source
4. Add layer > AWS layer/AWSSDKPANDAS-Python310/Version 8
5. Enter API key under "key":
6. Configuration > Permissions > Click Role_Name > Add permission (attach policy) > Search AmazonDyanmoDBFullAccess. (Full access for practice only)
7. Run Lambda test and verify if data received into DynamoDB table. Modify timeout to higher.
8. Search S3 > Create bucket with appropriate bucket name, keep default options, and create bucket
9. 
