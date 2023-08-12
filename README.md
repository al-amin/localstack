# localstack


[Download LocalStack from here]([https://link-url-here.org](https://github.com/localstack/localstack))

As of today : 02.06.2023 - I am using LocalStack 2.1.0\
As of today : 12.08.2023 - I am using LocalStack 2.2.0 ( localstack --version)

## Installation/Starting Localstack (Option 1)
The easiest way to install LocalStack is via pip:

```pip install localstack```\
```localstack start```

## Running localstack on Docker (Option 2) - I will be using this
```docker run --rm -it -p 4566:4566 -p 4571:4571 localstack/localstack```

## Installation/Starting Localstack using brew (Option 3) - currently I am using this - 12.08.2023
The easiest way to install LocalStack is via brew on MacOS:

```brew install localstack/tap/localstack-cli```\
```localstack --version```\
```localstack start```


# Using AWS CLI
## AWSLocal wrapper (Option #1)
```pip install awslocal-cli```\
```awslocal s3api list-buckets --region us-east-1```

## AWSLocal wrapper using pip3 on mac(Option #2) - currently I am using this - 12.08.2023
```pip3 install 'awscli-local[ver1]'```\
```awslocal s3api list-buckets --region us-east-1```

## AWS CLI pointing to endpoint (Option #3)
[Install and setup AWS CLI for LocalStack from here](https://docs.localstack.cloud/user-guide/integrations/aws-cli/)\

```
pip install awscli
YourMacUser ~ % export AWS_ACCESS_KEY_ID="test"
YourMacUser ~ % export AWS_SECRET_ACCESS_KEY="test"
YourMacUser ~ % export AWS_DEFAULT_REGION="us-east-1"
YourMacUser ~ % aws --endpoint-url=http://localhost:4566 kinesis list-streams
{
    "StreamNames": []
}
YourMacUser ~ % aws configure --profile default
AWS Access Key ID [None]: test
AWS Secret Access Key [None]: test
Default region name [None]: 
Default output format [None]: 

```

### Create your first bucket
```awslocal --endpoint-url=http://localhost:4566 s3api create-bucket --bucket my-bucket --region us-east-1```

### list the buckets:
```awslocal --endpoint-url=http://localhost:4566 s3api list-buckets```
