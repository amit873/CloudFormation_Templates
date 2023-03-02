# Commands -->>

## 1> Rule --> alf-S3PublicWrite
cfn-guard validate -d alf-S3PublicWrite.yaml -r alf-S3PublicWrite.guard
cfn-guard validate -d alf-S3ServerSideEncryption.yaml -r alf-S3PublicWrite.guard
#### Test
cfn-guard test --rules-file alf-S3PublicWrite.guard --test-data alf-S3PublicWrite-unit-test.yaml

## 2> Rule --> dl-bucket-public-check
cfn-guard validate -d dl-bucket-public-check.yaml -r dl-bucket-public-check.guard
#### Test
cfn-guard test --rules-file dl-bucket-public-check.guard --test-data dl-bucket-public-check-unit-test.yaml

## 3> Rule --> alf-S3ServerSideEncryption
cfn-guard validate -d alf-S3ServerSideEncryption.yaml -r alf-S3ServerSideEncryption.guard
#### Test
cfn-guard test --rules-file alf-S3ServerSideEncryption.guard --test-data alf-S3ServerSideEncryption-unit-test.yaml

## 4> Rule --> dl-s3-encryption
cfn-guard validate -d dl-s3-encryption.yaml -r dl-s3-encryption.guard
#### Test
cfn-guard test --rules-file dl-s3-encryption.guard --test-data dl-s3-encryption-unit-test.yaml

## 5> Rule --> dl-sns-encryption
cfn-guard validate -d dl-sns-encryption-AMK.yaml -r dl-sns-encryption.guard
cfn-guard validate -d dl-sns-encryption-CMK.yaml -r dl-sns-encryption.guard

cfn-guard validate -d Create-Topic-Subscription-AMK.yaml -r Create-Topic-Subscription.guard
cfn-guard validate -d Create-Topic-Subscription-CMK.yaml -r Create-Topic-Subscription.guard

#### Test
cfn-guard test --rules-file dl-sns-encryption.guard --test-data dl-sns-encryption-unit-test.yaml

#### Updated SNS
cfn-guard validate -d dl-sns-encryption-KMS.yaml -r dl-sns-encryption.guard
cfn-guard validate -d dl-sns-encryption-CLOUDHSM.yaml -r dl-sns-encryption.guard

cfn-guard test --rules-file dl-sns-encryption.guard --test-data dl-sns-encryption-unit-test.yaml

## 6> Rule --> dl-dynamodb-encryption
cfn-guard validate -d dl-dynamodb-encryption-AMK.yaml -r dl-dynamodb-encryption.guard
cfn-guard validate -d dl-dynamodb-encryption-CMK.yaml -r dl-dynamodb-encryption.guard

cfn-guard validate -d Create-DynamoDB-AMK.yaml -r dl-dynamodb-encryption.guard
cfn-guard validate -d Create-DynamoDB-CMK.yaml -r dl-dynamodb-encryption.guard

#### Test
cfn-guard test --rules-file dl-dynamodb-encryption.guard --test-data dl-dynamodb-encryption-unit-test.yaml

#### Updated DynamoDB
cfn-guard validate -d DynamoDB-Table-KMS.yaml -r dl-dynamodb-encryption.guard
cfn-guard validate -d DynamoDB-Table-CLOUDHSM.yaml -r dl-dynamodb-encryption.guard
###################
cfn-guard validate -d alf-S3PublicWrite.yaml -r dl-dynamodb-encryption.guard
cfn-guard validate -d alf-S3ServerSideEncryption.yaml -r dl-dynamodb-encryption.guard
###########################
cfn-guard test --rules-file dl-dynamodb-encryption.guard --test-data dl-dynamodb-encryption-unit-test.yaml

## 7> Rule --> dl-apigw-endpoint-private
cfn-guard validate -d dl-apigw-endpoint-private.yaml -r dl-apigw-endpoint-private.guard
#### Test
cfn-guard test --rules-file dl-apigw-endpoint-private.guard --test-data dl-apigw-endpoint-private-unit-test.yaml

## 8> Rule - S3-3 --> SSE
cfn-guard validate -d alf-S3ServerSideEncryption.yaml -r s3-bucket-sse.guard
cfn-guard validate -d dl-s3-encryption.yaml -r s3-bucket-sse.guard
#### Test
cfn-guard test --rules-file s3-bucket-sse.guard --test-data s3-bucket-sse-tests.yaml
