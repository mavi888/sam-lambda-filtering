# AWS Lambda Filtering

_Infrastructure as code framework used_: AWS SAM
_AWS Services used_: AWS Lambda, SQS, DynamoDB, DynamoDB Streams

## Summary of the demo

In this demo you will see:

- All the infrastructure needed to trigger a Lambda function using a SQS Queue.
- All the infrastructure needed to trigger a Lambda function using DynamoDB Streams
- How to configure event filtering for Lambda functions.

This demo is part of a video posted in FooBar Serverless channel. You can check the video to see the whole demo.

## Deploy this demo

We will be using AWS SAM and make sure you are running the latest version - at the time of writing, this was 1.37.0 (sam --version).

Deploy the project to the cloud:

```
sam deploy -g # Guided deployments
```

When asked about functions that may not have authorization defined, answer (y)es. The access to those functions will be open to anyone, so keep the app deployed only for the time you need this demo running.

Next times, when you update the code, you can build and deploy with:

```
sam deploy
```

To delete the app:

```
sam delete
```

## Commands used to send the SQS message

```
aws sqs send-message --queue-url https://sqs.us-west-2.amazonaws.com/<AccountID>/MyQueue --message-body "{ "data" : "A" }" --delay-seconds 10
```

## Links related to this code

- Video with more details: https://youtu.be/oY7vr0GMwjQ
- Launch blog post: https://aws.amazon.com/blogs/compute/filtering-event-sources-for-aws-lambda-functions/
