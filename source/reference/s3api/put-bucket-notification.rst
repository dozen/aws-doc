[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-notification:


***********************
put-bucket-notification
***********************



===========
Description
===========

Deprecated, see the PutBucketNotificationConfiguraiton operation.

========
Synopsis
========

::

    put-bucket-notification
  --bucket <value>
  [--content-md5 <value>]
  --notification-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--content-md5`` (string)


``--notification-configuration`` (structure)




Shorthand Syntax::

    TopicConfiguration={Id=string,Events=[string,string],Event=string,Topic=string},QueueConfiguration={Id=string,Event=string,Events=[string,string],Queue=string},CloudFunctionConfiguration={Id=string,Event=string,Events=[string,string],CloudFunction=string,InvocationRole=string}




JSON Syntax::

  {
    "TopicConfiguration": {
      "Id": "string",
      "Events": ["s3:ReducedRedundancyLostObject"|"s3:ObjectCreated:*"|"s3:ObjectCreated:Put"|"s3:ObjectCreated:Post"|"s3:ObjectCreated:Copy"|"s3:ObjectCreated:CompleteMultipartUpload"|"s3:ObjectRemoved:*"|"s3:ObjectRemoved:Delete"|"s3:ObjectRemoved:DeleteMarkerCreated", ...],
      "Event": "s3:ReducedRedundancyLostObject"|"s3:ObjectCreated:*"|"s3:ObjectCreated:Put"|"s3:ObjectCreated:Post"|"s3:ObjectCreated:Copy"|"s3:ObjectCreated:CompleteMultipartUpload"|"s3:ObjectRemoved:*"|"s3:ObjectRemoved:Delete"|"s3:ObjectRemoved:DeleteMarkerCreated",
      "Topic": "string"
    },
    "QueueConfiguration": {
      "Id": "string",
      "Event": "s3:ReducedRedundancyLostObject"|"s3:ObjectCreated:*"|"s3:ObjectCreated:Put"|"s3:ObjectCreated:Post"|"s3:ObjectCreated:Copy"|"s3:ObjectCreated:CompleteMultipartUpload"|"s3:ObjectRemoved:*"|"s3:ObjectRemoved:Delete"|"s3:ObjectRemoved:DeleteMarkerCreated",
      "Events": ["s3:ReducedRedundancyLostObject"|"s3:ObjectCreated:*"|"s3:ObjectCreated:Put"|"s3:ObjectCreated:Post"|"s3:ObjectCreated:Copy"|"s3:ObjectCreated:CompleteMultipartUpload"|"s3:ObjectRemoved:*"|"s3:ObjectRemoved:Delete"|"s3:ObjectRemoved:DeleteMarkerCreated", ...],
      "Queue": "string"
    },
    "CloudFunctionConfiguration": {
      "Id": "string",
      "Event": "s3:ReducedRedundancyLostObject"|"s3:ObjectCreated:*"|"s3:ObjectCreated:Put"|"s3:ObjectCreated:Post"|"s3:ObjectCreated:Copy"|"s3:ObjectCreated:CompleteMultipartUpload"|"s3:ObjectRemoved:*"|"s3:ObjectRemoved:Delete"|"s3:ObjectRemoved:DeleteMarkerCreated",
      "Events": ["s3:ReducedRedundancyLostObject"|"s3:ObjectCreated:*"|"s3:ObjectCreated:Put"|"s3:ObjectCreated:Post"|"s3:ObjectCreated:Copy"|"s3:ObjectCreated:CompleteMultipartUpload"|"s3:ObjectRemoved:*"|"s3:ObjectRemoved:Delete"|"s3:ObjectRemoved:DeleteMarkerCreated", ...],
      "CloudFunction": "string",
      "InvocationRole": "string"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The applies a notification configuration to a bucket named ``my-bucket``::

  aws s3api put-bucket-notification --bucket my-bucket --notification-configuration file://notification.json

The file ``notification.json`` is a JSON document in the current folder that specifies an SNS topic and an event type to monitor::

  {
    "TopicConfiguration": {
      "Event": "s3:ObjectCreated:*",
      "Topic": "arn:aws:sns:us-west-2:123456789012:s3-notification-topic"
    }
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