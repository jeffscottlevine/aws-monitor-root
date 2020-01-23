# Monitor AWS for Root Sign Ins and API Activity

## Overview

This CloudFormation template generates installs an AWS Lambda function
and an EventBridge rule that detects the following events and sends out
SNS notifications.

1. API calls made by the root user
2. Console logins by the root user

## CloudFormation parameters

The CloudFomration template prompts for these parameters.

1. The name of an SNS topic to create
2. The e-mail address to subscribe to the SNS topic

## Lambda function environment variables

The Lambda function that's installed uses two environment variables.

1. SNSARN - Initially set to the ARN of the SNS topic that is
provisioned by CloudFormation
2. LOGGING_LEVEL - The value to be passed to the Python logger()
function, initially set to DEBUG

## Authorship

An earlier verison of he code appeared on this blog post from
Sudhanshu Malhotra.

https://aws.amazon.com/blogs/mt/monitor-and-notify-on-aws-account-root-user-activity/

The code was subsequently revised by Jeffrey S. Levine.

## Additional notes

NOTE FOR CLOUDFORMATION STACKETS: If you intend to deploy this
template as part of a CloudFormation StackSet, please keep the
StackSet name short.  If you use a long StackSet name, the
resource names will exceed the 64 character limit and will cause
the deployment to fail.
