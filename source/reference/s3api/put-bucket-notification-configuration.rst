[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-notification-configuration:


*************************************
put-bucket-notification-configuration
*************************************



===========
Description
===========

Enables notifications of specified events for a bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketNotificationConfiguration>`_


========
Synopsis
========

::

    put-bucket-notification-configuration
  --bucket <value>
  --notification-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--notification-configuration`` (structure)
Container for specifying the notification configuration of the bucket. If this element is empty, notifications are turned off on the bucket.



JSON Syntax::

  {
    "TopicConfigurations": [
      {
        "Id": "string",
        "TopicArn": "string",
        "Events": ["s3:ReducedRedundancyLostObject"|"s3:ObjectCreated:*"|"s3:ObjectCreated:Put"|"s3:ObjectCreated:Post"|"s3:ObjectCreated:Copy"|"s3:ObjectCreated:CompleteMultipartUpload"|"s3:ObjectRemoved:*"|"s3:ObjectRemoved:Delete"|"s3:ObjectRemoved:DeleteMarkerCreated", ...],
        "Filter": {
          "Key": {
            "FilterRules": [
              {
                "Name": "prefix"|"suffix",
                "Value": "string"
              }
              ...
            ]
          }
        }
      }
      ...
    ],
    "QueueConfigurations": [
      {
        "Id": "string",
        "QueueArn": "string",
        "Events": ["s3:ReducedRedundancyLostObject"|"s3:ObjectCreated:*"|"s3:ObjectCreated:Put"|"s3:ObjectCreated:Post"|"s3:ObjectCreated:Copy"|"s3:ObjectCreated:CompleteMultipartUpload"|"s3:ObjectRemoved:*"|"s3:ObjectRemoved:Delete"|"s3:ObjectRemoved:DeleteMarkerCreated", ...],
        "Filter": {
          "Key": {
            "FilterRules": [
              {
                "Name": "prefix"|"suffix",
                "Value": "string"
              }
              ...
            ]
          }
        }
      }
      ...
    ],
    "LambdaFunctionConfigurations": [
      {
        "Id": "string",
        "LambdaFunctionArn": "string",
        "Events": ["s3:ReducedRedundancyLostObject"|"s3:ObjectCreated:*"|"s3:ObjectCreated:Put"|"s3:ObjectCreated:Post"|"s3:ObjectCreated:Copy"|"s3:ObjectCreated:CompleteMultipartUpload"|"s3:ObjectRemoved:*"|"s3:ObjectRemoved:Delete"|"s3:ObjectRemoved:DeleteMarkerCreated", ...],
        "Filter": {
          "Key": {
            "FilterRules": [
              {
                "Name": "prefix"|"suffix",
                "Value": "string"
              }
              ...
            ]
          }
        }
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The applies a notification configuration to a bucket named ``my-bucket``::

  aws s3api put-bucket-notification-configuration --bucket my-bucket --notification-configuration file://notification.json

The file ``notification.json`` is a JSON document in the current folder that specifies an SNS topic and an event type to monitor::

  {
     "TopicConfigurations": [
         {
             "TopicArn": "arn:aws:sns:us-west-2:123456789012:s3-notification-topic",
             "Events": [
                 "s3:ObjectCreated:*"
             ]
         }
     ]
 }

The SNS topic must have an IAM policy attached to it that allows Amazon S3 to publish to it::

  {
   "Version": "2008-10-17",
   "Id": "example-ID",
   "Statement": [
    {
     "Sid": "example-statement-ID",
     "Effect": "Allow",
     "Principal": {
       "Service": "s3.amazonaws.com"  
     },
     "Action": [
      "SNS:Publish"
     ],
     "Resource": "arn:aws:sns:us-west-2:123456789012:my-bucket",
     "Condition": {
        "ArnLike": {          
        "aws:SourceArn": "arn:aws:s3:*:*:my-bucket"    
      }
     }
    }
   ]
  }

======
Output
======

None