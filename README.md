# You must have Active AWS account. Try to read about AWS Rekognition
# Commands

* Install aws shell
```
pip install aws-shell
```
* Configure Aws with your access key, secret access key, region and token

```
aws configure
```
> It will ask for credinationals

* Create a collection on aws rekognition
```
aws rekognition create-collection --collection-id facerecognition_collection --region us-east-1
```
* Create table on DynamoDB
```
aws dynamodb create-table --table-name facerecognition \
--attribute-definitions AttributeName=RekognitionId,AttributeType=S \
--key-schema AttributeName=RekognitionId,KeyType=HASH \
--provisioned-throughput ReadCapacityUnits=1,WriteCapacityUnits=1 \
--region us-east-1

```

* Create S3 bucket
```
aws s3 mb s3://bucket-name --region us-east-1
```
