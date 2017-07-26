[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail create-subscription:


*******************
create-subscription
*******************



===========
Description
===========

Creates and configures the AWS resources necessary to use CloudTrail, creates a trail using those resources, and turns on logging.



========
Synopsis
========

::

    aws cloudtrail create-subscription (--s3-use-bucket|--s3-new-bucket) bucket-name [--sns-new-topic topic-name]





=======
Options
=======

``--name`` (string)
Cloudtrail name

``--s3-new-bucket`` (string)
Create a new S3 bucket with this name

``--s3-use-bucket`` (string)
Use an existing S3 bucket with this name

``--s3-prefix`` (string)
S3 object prefix

``--sns-new-topic`` (string)
Create a new SNS topic with this name

``--include-global-service-events`` (string)
Whether to include global service events

``--s3-custom-policy`` (string)
Custom S3 policy template or URL

``--sns-custom-policy`` (string)
Custom SNS policy template or URL



========
Examples
========

**To create and configure AWS resources for a trail**

The following ``create-subscription`` command creates a new S3 bucket and SNS topic for ``Trail1``::

  aws cloudtrail create-subscription --name Trail1 --s3-new-bucket my-bucket --sns-new-topic my-topic

Output::

  Setting up new S3 bucket my-bucket...
  Setting up new SNS topic my-topic...
  Creating/updating CloudTrail configuration...
  CloudTrail configuration:
  {
  "trailList": [ 
    {
      "IncludeGlobalServiceEvents": true, 
      "Name": "Trail1", 
      "TrailARN": "arn:aws:cloudtrail:us-east-1:123456789012:trail/Trail1", 
      "LogFileValidationEnabled": false, 
      "IsMultiRegionTrail": false, 
      "S3BucketName": "my-bucket", 
      "SnsTopicName": "my-topic", 
      "HomeRegion": "us-east-1"
    }
  ], 
  "ResponseMetadata": {
  "HTTPStatusCode": 200, 
  "RequestId": "f39e51f6-c615-11e5-85bd-d35ca21ee3e2"
  }
  }
  Starting CloudTrail service...
  Logs will be delivered to my-bucket