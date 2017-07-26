[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail update-subscription:


*******************
update-subscription
*******************



===========
Description
===========

Updates any of the trail configuration settings, and creates and configures any new AWS resources specified.



========
Synopsis
========

::

    aws cloudtrail update-subscription [(--s3-use-bucket|--s3-new-bucket) bucket-name] [--sns-new-topic topic-name]





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

**To update the configuration settings for a trail**

The following ``update-subscription`` command updates the trail to specify a new S3 bucket and SNS topic::

  aws cloudtrail update-subscription --name Trail1 --s3-new-bucket my-bucket-new --sns-new-topic my-topic-new

Output::

  Setting up new S3 bucket my-bucket-new...
  Setting up new SNS topic my-topic-new...
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
      "S3BucketName": "my-bucket-new", 
      "SnsTopicName": "my-topic-new", 
      "HomeRegion": "us-east-1"
    }
  ], 
  "ResponseMetadata": {
  "HTTPStatusCode": 200, 
  "RequestId": "31126f8a-c616-11e5-9cc6-2fd637936879"
  }
  }