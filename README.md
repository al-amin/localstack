# localstack


[Download LocalStack from here]([https://link-url-here.org](https://github.com/localstack/localstack))

As of today : 02.06.2023 - I am using LocalStack 2.1.0

## Installation/Starting Localstack (Option 1)
The easiest way to install LocalStack is via pip:

```pip install localstack```\
```localstack start```

## Running localstack on Docker (Option 2) - I will be using this
```docker run --rm -it -p 4566:4566 -p 4571:4571 localstack/localstack```

# Using AWS CLI
## AWSLocal wrapper (Option #1)
```pip install awslocal-cli```\
```awslocal s3api list-buckets --region us-east-1```

## AWS CLI pointing to endpoint (Option #2)
```pip install awscli```\
```aws --endpoint-url=http://localhost:4566 s3api create-bucket --bucket my-bucket --region us-east-1```
