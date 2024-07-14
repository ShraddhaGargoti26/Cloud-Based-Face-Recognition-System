# Cloud-Based-Face-Recognition-System
A cloud-based face recognition system using AWS leverages Amazon Rekognition for accurate facial analysis, AWS Lambda for serverless computing, and AWS S3 for storage. This system can detect, recognize, and compare faces in images or videos, making it ideal for applications like security, access control, and social media tagging.

#COMMANDS


- Install aws-shell
```
pip install aws-shell
```

- Configure
```
aws configure
```

- Create a collection on aws rekognition
```
aws rekognition create-collection --collection-id facerecognition_collection --region us-east-1
```

- Create table on DynamoDB
```
aws dynamodb create-table --table-name facerecognition \
--attribute-definitions AttributeName=RekognitionId,AttributeType=S \
--key-schema AttributeName=RekognitionId,KeyType=HASH \
--provisioned-throughput ReadCapacityUnits=1,WriteCapacityUnits=1 \
--region us-east-1
```

- Create S3 bucket
```
aws s3 mb s3://bucket-name --region us-east-1
```
