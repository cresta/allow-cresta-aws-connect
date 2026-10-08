# Allow Cresta Amazon Connect Data Access

[![Launch Stack](https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png)](https://console.aws.amazon.com/cloudformation/home#/stacks/create/review?stackName=allow-cresta-aws-connect&templateURL=https://cresta-cloudformation-template.s3.amazonaws.com/allow-cresta-aws-connect/aws/main.yaml)

This template creates the following AWS resource and policies required by the Cresta AWS Data Access Integration:

- Policy to read from the S3 bucket in your AWS account for read access to
  -  the AWS Connect Instance
  -  the AWS S3 Bucket holding the recordings / transcriptions
- An IAM role for Cresta to assume 

## Steps to Deploy

1. Log into your admin AWS account/role
2. Switch to the same AWS Region as your Amazon Connect instance
3. Deploy the CloudFormation Stack with the `Launch Stack` button above
4. Fill in the parameters using the table below
5. Click Create stack

| Parameter | What to enter | Example |
| --- | --- | --- |
| `SourceBucketName` | The S3 bucket name only. Do not include `s3://` or a folder path. | `acme-connect-recordings` |
| `ConnectInstanceId` | The value after `instance/` in the Amazon Connect instance ARN. | `12345678-1234-1234-1234-123456789012` |
| `ExternalId` | The external ID provided by your Cresta account manager, or leave blank if none was provided. | `acme-connect` |
| `IAMRoleName` | Keep the default unless instructed otherwise. | `CrestaIngestionRole` |
| `CrestaAWSAccountIds` | Keep the prefilled value unchanged. | No change needed |

Wait for the stack creation to complete.
Then, in CloudFormation Stack view:

1. Click on the `Outputs` tab
2. Take a screenshot of the outputs
3. Provide the screenshot to your Cresta account manager
