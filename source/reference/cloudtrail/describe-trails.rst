[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail describe-trails:


***************
describe-trails
***************



===========
Description
===========



Retrieves settings for the trail associated with the current region for your account.



========
Synopsis
========

::

    describe-trails
  [--trail-name-list <value>]
  [--include-shadow-trails | --no-include-shadow-trails]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--trail-name-list`` (list)


  Specifies a list of trail names, trail ARNs, or both, of the trails to describe. The format of a trail ARN is ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail`` . If an empty list is specified, information for the trail in the current region is returned.

   

   
  * If an empty list is specified and ``IncludeShadowTrails`` is false, then information for all trails in the current region is returned.
   
  * If an empty list is specified and IncludeShadowTrails is null or true, then information for all trails in the current region and any associated shadow trails in other regions is returned. 
   

   

  .. note::

    If one or more trail names are specified, information is returned only if the names match the names of trails belonging only to the current region. To return information about a trail in another region, you must specify its trail ARN.

  



Syntax::

  "string" "string" ...



``--include-shadow-trails`` | ``--no-include-shadow-trails`` (boolean)


  Specifies whether to include shadow trails in the response. A shadow trail is the replication in a region of a trail that was created in a different region. The default is true.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

trailList -> (list)

  

  The list of trail objects.

  

  (structure)

    

    The settings for a trail.

    

    Name -> (string)

      

      Name of the trail set by calling  create-trail . The maximum length is 128 characters.

      

      

    S3BucketName -> (string)

      

      Name of the Amazon S3 bucket into which CloudTrail delivers your trail files. See `Amazon S3 Bucket Naming Requirements`_ .

      

      

    S3KeyPrefix -> (string)

      

      Specifies the Amazon S3 key prefix that comes after the name of the bucket you have designated for log file delivery. For more information, see `Finding Your CloudTrail Log Files`_ .The maximum length is 200 characters.

      

      

    SnsTopicName -> (string)

      

      Name of the existing Amazon SNS topic that CloudTrail uses to notify the account owner when new CloudTrail log files have been delivered. The maximum length is 256 characters.

      

      

    IncludeGlobalServiceEvents -> (boolean)

      

      Set to **True** to include AWS API calls from AWS global services such as IAM. Otherwise, **False** .

      

      

    IsMultiRegionTrail -> (boolean)

      

      Specifies whether the trail belongs only to one region or exists in all regions.

      

      

    HomeRegion -> (string)

      

      The region in which the trail was created.

      

      

    TrailARN -> (string)

      

      The Amazon Resource Name of the trail. The ``TrailARN`` format is ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail`` .

      

      

    LogFileValidationEnabled -> (boolean)

      

      Specifies whether log file validation is enabled.

      

      

    CloudWatchLogsLogGroupArn -> (string)

      

      Specifies an Amazon Resource Name (ARN), a unique identifier that represents the log group to which CloudTrail logs will be delivered.

      

      

    CloudWatchLogsRoleArn -> (string)

      

      Specifies the role for the CloudWatch Logs endpoint to assume to write to a user's log group.

      

      

    KmsKeyId -> (string)

      

      Specifies the KMS key ID that encrypts the logs delivered by CloudTrail. The value is a fully specified ARN to a KMS key in the format:

       ``arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012`` 

      

    

  



.. _Amazon S3 Bucket Naming Requirements: http://docs.aws.amazon.com/awscloudtrail/latest/userguide/create_trail_naming_policy.html
.. _Finding Your CloudTrail Log Files: http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-find-log-files.html
