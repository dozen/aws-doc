[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail describe-trails:


***************
describe-trails
***************



===========
Description
===========



Retrieves settings for the trail associated with the current region for your account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudtrail-2013-11-01/DescribeTrails>`_


========
Synopsis
========

::

    describe-trails
  [--trail-name-list <value>]
  [--include-shadow-trails | --no-include-shadow-trails]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--trail-name-list`` (list)


  Specifies a list of trail names, trail ARNs, or both, of the trails to describe. The format of a trail ARN is:

   

   ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail``  

   

  If an empty list is specified, information for the trail in the current region is returned.

   

   
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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a trail**

The following ``describe-trails`` command returns the settings for ``Trail1`` and ``Trail2``::

  aws cloudtrail describe-trails --trail-name-list Trail1 Trail2

Output::

  {
   "trailList": [
       {
           "IncludeGlobalServiceEvents": true, 
           "Name": "Trail1", 
           "TrailARN": "arn:aws:cloudtrail:us-east-1:123456789012:trail/Trail1", 
           "LogFileValidationEnabled": false, 
           "IsMultiRegionTrail": false, 
           "S3BucketName": "my-bucket", 
           "CloudWatchLogsRoleArn": "arn:aws:iam::123456789012:role/CloudTrail_CloudWatchLogs_Role", 
           "CloudWatchLogsLogGroupArn": "arn:aws:logs:us-east-1:123456789012:log-group:CloudTrail:*", 
           "SnsTopicName": "my-topic", 
           "HomeRegion": "us-east-1"
       }, 
       {
           "IncludeGlobalServiceEvents": true, 
           "Name": "Trail2", 
           "S3KeyPrefix": "my-prefix", 
           "TrailARN": "arn:aws:cloudtrail:us-east-1:123456789012:trail/Trail2", 
           "LogFileValidationEnabled": false, 
           "IsMultiRegionTrail": false, 
           "S3BucketName": "my-bucket", 
           "KmsKeyId": "arn:aws:kms:us-east-1:123456789012:key/4c5ae5ac-3c13-421e-8335-c7868ef6a769", 
           "HomeRegion": "us-east-1"
       }
    ]
  }

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

      

      Name of the Amazon S3 bucket into which CloudTrail delivers your trail files. See `Amazon S3 Bucket Naming Requirements <http://docs.aws.amazon.com/awscloudtrail/latest/userguide/create_trail_naming_policy.html>`_ .

      

      

    S3KeyPrefix -> (string)

      

      Specifies the Amazon S3 key prefix that comes after the name of the bucket you have designated for log file delivery. For more information, see `Finding Your CloudTrail Log Files <http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-find-log-files.html>`_ .The maximum length is 200 characters.

      

      

    SnsTopicName -> (string)

      

      This field is deprecated. Use SnsTopicARN.

      

      

    SnsTopicARN -> (string)

      

      Specifies the ARN of the Amazon SNS topic that CloudTrail uses to send notifications when log files are delivered. The format of a topic ARN is:

       

       ``arn:aws:sns:us-east-1:123456789012:MyTopic``  

      

      

    IncludeGlobalServiceEvents -> (boolean)

      

      Set to **True** to include AWS API calls from AWS global services such as IAM. Otherwise, **False** .

      

      

    IsMultiRegionTrail -> (boolean)

      

      Specifies whether the trail belongs only to one region or exists in all regions.

      

      

    HomeRegion -> (string)

      

      The region in which the trail was created.

      

      

    TrailARN -> (string)

      

      Specifies the ARN of the trail. The format of a trail ARN is:

       

       ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail``  

      

      

    LogFileValidationEnabled -> (boolean)

      

      Specifies whether log file validation is enabled.

      

      

    CloudWatchLogsLogGroupArn -> (string)

      

      Specifies an Amazon Resource Name (ARN), a unique identifier that represents the log group to which CloudTrail logs will be delivered.

      

      

    CloudWatchLogsRoleArn -> (string)

      

      Specifies the role for the CloudWatch Logs endpoint to assume to write to a user's log group.

      

      

    KmsKeyId -> (string)

      

      Specifies the KMS key ID that encrypts the logs delivered by CloudTrail. The value is a fully specified ARN to a KMS key in the format:

       

       ``arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012``  

      

      

    HasCustomEventSelectors -> (boolean)

      

      Specifies if the trail has custom event selectors.

      

      

    

  

