# Amazon DynamoDB Table Template

Use Amazon DynamoDB CloudFormation template to declare DynamoDB for use in your application. You need to update the template based on you application specific Attributes, Names etc. 
There are samples to create DynamoDB table.

## DynamoDB Table
Amazon DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability. DynamoDB lets you offload the administrative burdens of operating and scaling a distributed database so that you don't have to worry about hardware provisioning, setup and configuration, replication, software patching, or cluster scaling. DynamoDB also offers encryption at rest, which eliminates the operational burden and complexity involved in protecting sensitive dataacity.

The template accepts two parameters as inputs as described below

### Parameters
1. ReadCapacityUnits: Provisioned throughput is the maximum amount of capacity that an application can consume from a table or index. If your   application exceeds your provisioned throughput capacity on a table or index, it is subject to request throttling. ReadCapacityUnits is one of the parameter through which you can mention read capacity of DynamoDB Table or Index at the time of provisioning. Default value considered here is 10
2. WriteCapacityUnits: WriteCapacityUnits is one of the parameter through which you can mention write capacity of DynamoDB Table or Index at the time of provisioning. Default value considered here is 10
3. DBTableName1: Give the table Name for first table which you want to create for DynamoDB.
4. DBTableName2: Give the table Name for second table which you want to create for DynamoDB.
5. CreatesecondTable: Give the valus as true if you want to create second table or else false if only 1 table is required.
