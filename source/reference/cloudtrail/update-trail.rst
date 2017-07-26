[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail update-trail:


************
update-trail
************



===========
Description
===========



Updates the settings that specify delivery of log files. Changes to a trail do not require stopping the CloudTrail service. Use this action to designate an existing bucket for log delivery. If the existing bucket has previously been a target for CloudTrail log files, an IAM policy exists for the bucket. ``update-trail`` must be called from the region in which the trail was created; otherwise, an ``InvalidHomeRegionException`` is thrown.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudtrail-2013-11-01/UpdateTrail>`_


========
Synopsis
========

::

    update-trail
  --name <value>
  [--s3-bucket-name <value>]
  [--s3-key-prefix <value>]
  [--sns-topic-name <value>]
  [--include-global-service-events | --no-include-global-service-events]
  [--is-multi-region-trail | --no-is-multi-region-trail]
  [--enable-log-file-validation | --no-enable-log-file-validation]
  [--cloud-watch-logs-log-group-arn <value>]
  [--cloud-watch-logs-role-arn <value>]
  [--kms-key-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Specifies the name of the trail or trail ARN. If ``Name`` is a trail name, the string must meet the following requirements:

   

   
  * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-) 
   
  * Start with a letter or number, and end with a letter or number 
   
  * Be between 3 and 128 characters 
   
  * Have no adjacent periods, underscores or dashes. Names like ``my-_namespace`` and ``my--namespace`` are invalid. 
   
  * Not be in IP address format (for example, 192.168.5.4) 
   

   

  If ``Name`` is a trail ARN, it must be in the format:

   

   ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail``  

  

``--s3-bucket-name`` (string)


  Specifies the name of the Amazon S3 bucket designated for publishing log files. See `Amazon S3 Bucket Naming Requirements <http://docs.aws.amazon.com/awscloudtrail/latest/userguide/create_trail_naming_policy.html>`_ .

  

``--s3-key-prefix`` (string)


  Specifies the Amazon S3 key prefix that comes after the name of the bucket you have designated for log file delivery. For more information, see `Finding Your CloudTrail Log Files <http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-find-log-files.html>`_ . The maximum length is 200 characters.

  

``--sns-topic-name`` (string)


  Specifies the name of the Amazon SNS topic defined for notification of log file delivery. The maximum length is 256 characters.

  

``--include-global-service-events`` | ``--no-include-global-service-events`` (boolean)


  Specifies whether the trail is publishing events from global services such as IAM to the log files.

  

``--is-multi-region-trail`` | ``--no-is-multi-region-trail`` (boolean)


  Specifies whether the trail applies only to the current region or to all regions. The default is false. If the trail exists only in the current region and this value is set to true, shadow trails (replications of the trail) will be created in the other regions. If the trail exists in all regions and this value is set to false, the trail will remain in the region where it was created, and its shadow trails in other regions will be deleted.

  

``--enable-log-file-validation`` | ``--no-enable-log-file-validation`` (boolean)


  Specifies whether log file validation is enabled. The default is false.

   

  .. note::

     

    When you disable log file integrity validation, the chain of digest files is broken after one hour. CloudTrail will not create digest files for log files that were delivered during a period in which log file integrity validation was disabled. For example, if you enable log file integrity validation at noon on January 1, disable it at noon on January 2, and re-enable it at noon on January 10, digest files will not be created for the log files delivered from noon on January 2 to noon on January 10. The same applies whenever you stop CloudTrail logging or delete a trail.

     

  

``--cloud-watch-logs-log-group-arn`` (string)


  Specifies a log group name using an Amazon Resource Name (ARN), a unique identifier that represents the log group to which CloudTrail logs will be delivered. Not required unless you specify CloudWatchLogsRoleArn.

  

``--cloud-watch-logs-role-arn`` (string)


  Specifies the role for the CloudWatch Logs endpoint to assume to write to a user's log group.

  

``--kms-key-id`` (string)


  Specifies the KMS key ID to use to encrypt the logs delivered by CloudTrail. The value can be an alias name prefixed by "alias/", a fully specified ARN to an alias, a fully specified ARN to a key, or a globally unique identifier.

   

  Examples:

   

   
  * alias/MyAliasName 
   
  * arn:aws:kms:us-east-1:123456789012:alias/MyAliasName 
   
  * arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
   
  * 12345678-1234-1234-1234-123456789012 
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update a trail**

The following ``update-trail`` command updates a trail to use an existing bucket for log delivery::

  aws cloudtrail update-trail --name Trail1 --s3-bucket-name my-bucket

Output::

  {
    "IncludeGlobalServiceEvents": true, 
    "Name": "Trail1", 
    "TrailARN": "arn:aws:cloudtrail:us-west-2:123456789012:trail/Trail1", 
    "LogFileValidationEnabled": false, 
    "IsMultiRegionTrail": true, 
    "S3BucketName": "my-bucket"
  }

======
Output
======

Name -> (string)

  

  Specifies the name of the trail.

  

  

S3BucketName -> (string)

  

  Specifies the name of the Amazon S3 bucket designated for publishing log files.

  

  

S3KeyPrefix -> (string)

  

  Specifies the Amazon S3 key prefix that comes after the name of the bucket you have designated for log file delivery. For more information, see `Finding Your CloudTrail Log Files <http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-find-log-files.html>`_ .

  

  

SnsTopicName -> (string)

  

  This field is deprecated. Use SnsTopicARN.

  

  

SnsTopicARN -> (string)

  

  Specifies the ARN of the Amazon SNS topic that CloudTrail uses to send notifications when log files are delivered. The format of a topic ARN is:

   

   ``arn:aws:sns:us-east-1:123456789012:MyTopic``  

  

  

IncludeGlobalServiceEvents -> (boolean)

  

  Specifies whether the trail is publishing events from global services such as IAM to the log files.

  

  

IsMultiRegionTrail -> (boolean)

  

  Specifies whether the trail exists in one region or in all regions.

  

  

TrailARN -> (string)

  

  Specifies the ARN of the trail that was updated. The format of a trail ARN is:

   

   ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail``  

  

  

LogFileValidationEnabled -> (boolean)

  

  Specifies whether log file integrity validation is enabled.

  

  

CloudWatchLogsLogGroupArn -> (string)

  

  Specifies the Amazon Resource Name (ARN) of the log group to which CloudTrail logs will be delivered.

  

  

CloudWatchLogsRoleArn -> (string)

  

  Specifies the role for the CloudWatch Logs endpoint to assume to write to a user's log group.

  

  

KmsKeyId -> (string)

  

  Specifies the KMS key ID that encrypts the logs delivered by CloudTrail. The value is a fully specified ARN to a KMS key in the format:

   

   ``arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012``  

  

  

