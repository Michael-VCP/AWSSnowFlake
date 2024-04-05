# AWSSnowFlake

Reference: https://www.youtube.com/watch?v=zc61fvbmSoc&list=WL&index=61

## Architecture Defined

## Servives Used

## Architecture Break Down

1. Search DynamoDB > Create table > Create table name as api name
2. Partiotion key (Partition key + Sort key = Primary key) > City and Time > Default settings > Create table
3. Search Lambda > Create function > Enter name > Python 3.10 > Create function > Test function, Invoke function, and modify code source
4. Add layer > AWS layer/AWSSDKPANDAS-Python310/Version 8
5. Enter API key under "key":
6. Configuration > Permissions > Click Role_Name > Add permission (attach policy) > Search AmazonDyanmoDBFullAccess. (Full access for practice only)
7. Run Lambda test and verify if data received into DynamoDB table. Modify timeout to higher.
8. Search S3 > Create bucket with appropriate bucket name, keep default options, and create bucket
9. Open bucket > Create folder > Name folder as SnowFlake > Submit create folder
10. Search Lambda > Create new fuction > Create name as DDBtoSnowFlake > Python310/Version 8 > Modify Lambda code
11. Add layer > AWS layer/AWSSDKPANDAS-Python310/Version 8
12. Configuration > Permissions > Click Role_Name > Add permission (attach policy) > Search AmazonS3FullAccess & DynamoDBFullAccess permissions. (Full access for practice only)
13. Modify timeout to 15 seconds/Modify memory to 150 to 250 MB
15. Add trigger in Lambda > Source is Dynamo DB > Use created DynamoDB table/Batch size 5. Test code.
16. Amazon S3 > Buckets > Project folder > Snowflake to verify if data transferred over
17. Open SnowFlake website
18. Search IAM > Roles > Create role for AWS > Attach AmazonS3FullAccess
19. Go into newly created role > Copy ARN > Copy and paste into Snowflake
20. Go to S3 bucket you created > Copy S3 URI and paste into Snowflake > Enter
21. Copy role ARN from SnowFlake > AWS Trustrelationship > Paste ARN > Add condition externalid > Update policy (Helps AWS authenticate SnowFlake)
22. In SnowFlake, create or replace file format csv_format > Run code to successfully create
23. In SnowFlake, Define stage ext_csv_stage > Run code
24. In SnowFLake, create snow pipe > Run code
25. Describe integration s3_int > Run code > Copy and paste storage_aws_IAM_user_ARN into AWS
26. Show pipes for notification_channel > Go to AWS bucket > Properties > Create event notification > Check box for all objects to alert and SQS queque topic: Snowpipe copy/paste
27. Search your Lambda function to invoke and test (Any data placed into DynamoDB table is automatically transferred to SnowFlake)
28. Search your Lambda function > Add trigger > new rule > trigger_every_hour > s

