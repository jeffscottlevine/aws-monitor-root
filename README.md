# RootAPIMonitor.yaml - Monitor AWS for Root Sign Ins and API Activity

## Overview

This CloudFormation generates installs an AWS Lambda function and an
EventBridge rule that detects the following events and sends out SNS
notifications.

1. API calls made by the root user
2. Console logins by the root user

## Environment Variables

The Lambda function also checks the following variables:

LOGGING_LEVEL (optional, default DEBUG) - the Python logger
value

SNSARN - The AWS SNS Topic ARN for sending messages

## Authorship

An earlier verison of he code appeared on this blog post from
Sudhanshu Malhotra.

https://aws.amazon.com/blogs/mt/monitor-and-notify-on-aws-account-root-user-activity/

The code was subsequently revised by Jeffrey S. Levine.

## Additional Notes

NOTE FOR CLOUDFORMATION STACKETS: If you intend to deploy this
template as part of a CloudFormation StackSet, please keep the
StackSet name short.  If you use a long StackSet name, the
resource names will exceed the 64 character limit and will cause
the deployment to fail.
