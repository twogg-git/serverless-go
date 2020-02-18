# serverless-go
Some simple examples with Go AWS and Lambda



https://serverless.com/examples/
https://github.com/serverless/serverless


https://github.com/serverless/examples/tree/master/aws-java-simple-http-endpoint

https://nodejs.org/en/download/

https://console.aws.amazon.com/lambda/home?region=us-east-1#/applications

https://github.com/serverless/serverless/blob/master/docs/providers/aws/guide/credentials.md
export AWS_ACCESS_KEY_ID=<your-key-here>
export AWS_SECRET_ACCESS_KEY=<your-secret-key-here>

mkdir .aws
vim credentials

[endava-med-aws]
aws_access_key_id = <your-key-here>
aws_secret_access_key = <your-secret-key-here>

serverless deploy --aws-profile endava-med-aws

curl https://zf6oolkvn6.execute-api.us-east-1.amazonaws.com/dev/ping

serverless remove --aws-profile endava-med-aws


Learning Objectives
check_circle
Create IAM Role for Lambda
keyboard_arrow_up
If a Lambda function needs to call other AWS services, we need to create an IAM role that it can assume at execution time.

Create an IAM role for our Lambda function to be able to connect with S3, Amazon Transcribe, and CloudWatch Logs:

Navigate to the IAM console page.
Select Roles from the left-hand menu.
Select Create role.
Select Lambda as the trusted entity.

Add the following managed policies:
-AmazonS3ReadOnlyAccess
-AmazonTranscribeFullAccess
-CloudWatchLogsFullAccess

Name the role "lab-lambda-role".
