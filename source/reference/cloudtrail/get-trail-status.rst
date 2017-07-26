[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail get-trail-status:


****************
get-trail-status
****************



===========
Description
===========



Returns a JSON-formatted list of information about the specified trail. Fields include information on delivery errors, Amazon SNS and Amazon S3 errors, and start and stop logging times for each trail. This operation returns trail status from a single region. To return trail status from all regions, you must call the operation on each region.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudtrail-2013-11-01/GetTrailStatus>`_


========
Synopsis
========

::

    get-trail-status
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Specifies the name or the CloudTrail ARN of the trail for which you are requesting status. To get the status of a shadow trail (a replication of the trail in another region), you must specify its ARN. The format of a trail ARN is:

   

   ``arn:aws:cloudtrail:us-east-1:123456789012:trail/MyTrail``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the status of a trail**

The following ``get-trail-status`` command returns the delivery and logging details for ``Trail1``::

  aws cloudtrail get-trail-status --name Trail1

Output::

  {
    "LatestNotificationTime": 1454022144.869, 
    "LatestNotificationAttemptSucceeded": "2016-01-28T23:02:24Z", 
    "LatestDeliveryAttemptTime": "2016-01-28T23:02:24Z", 
    "LatestDeliveryTime": 1454022144.869, 
    "TimeLoggingStarted": "2015-11-06T18:36:38Z", 
    "LatestDeliveryAttemptSucceeded": "2016-01-28T23:02:24Z", 
    "IsLogging": true, 
    "LatestCloudWatchLogsDeliveryTime": 1454022144.918, 
    "StartLoggingTime": 1446834998.695, 
    "StopLoggingTime": 1446834996.933, 
    "LatestNotificationAttemptTime": "2016-01-28T23:02:24Z", 
    "TimeLoggingStopped": "2015-11-06T18:36:36Z"
  }

======
Output
======

IsLogging -> (boolean)

  

  Whether the CloudTrail is currently logging AWS API calls.

  

  

LatestDeliveryError -> (string)

  

  Displays any Amazon S3 error that CloudTrail encountered when attempting to deliver log files to the designated bucket. For more information see the topic `Error Responses <http://docs.aws.amazon.com/AmazonS3/latest/API/ErrorResponses.html>`_ in the Amazon S3 API Reference. 

   

  .. note::

     

    This error occurs only when there is a problem with the destination S3 bucket and will not occur for timeouts. To resolve the issue, create a new bucket and call ``update-trail`` to specify the new bucket, or fix the existing objects so that CloudTrail can again write to the bucket.

     

  

  

LatestNotificationError -> (string)

  

  Displays any Amazon SNS error that CloudTrail encountered when attempting to send a notification. For more information about Amazon SNS errors, see the `Amazon SNS Developer Guide <http://docs.aws.amazon.com/sns/latest/dg/welcome.html>`_ . 

  

  

LatestDeliveryTime -> (timestamp)

  

  Specifies the date and time that CloudTrail last delivered log files to an account's Amazon S3 bucket.

  

  

LatestNotificationTime -> (timestamp)

  

  Specifies the date and time of the most recent Amazon SNS notification that CloudTrail has written a new log file to an account's Amazon S3 bucket.

  

  

StartLoggingTime -> (timestamp)

  

  Specifies the most recent date and time when CloudTrail started recording API calls for an AWS account.

  

  

StopLoggingTime -> (timestamp)

  

  Specifies the most recent date and time when CloudTrail stopped recording API calls for an AWS account.

  

  

LatestCloudWatchLogsDeliveryError -> (string)

  

  Displays any CloudWatch Logs error that CloudTrail encountered when attempting to deliver logs to CloudWatch Logs.

  

  

LatestCloudWatchLogsDeliveryTime -> (timestamp)

  

  Displays the most recent date and time when CloudTrail delivered logs to CloudWatch Logs.

  

  

LatestDigestDeliveryTime -> (timestamp)

  

  Specifies the date and time that CloudTrail last delivered a digest file to an account's Amazon S3 bucket.

  

  

LatestDigestDeliveryError -> (string)

  

  Displays any Amazon S3 error that CloudTrail encountered when attempting to deliver a digest file to the designated bucket. For more information see the topic `Error Responses <http://docs.aws.amazon.com/AmazonS3/latest/API/ErrorResponses.html>`_ in the Amazon S3 API Reference. 

   

  .. note::

     

    This error occurs only when there is a problem with the destination S3 bucket and will not occur for timeouts. To resolve the issue, create a new bucket and call ``update-trail`` to specify the new bucket, or fix the existing objects so that CloudTrail can again write to the bucket.

     

  

  

LatestDeliveryAttemptTime -> (string)

  

  This field is deprecated.

  

  

LatestNotificationAttemptTime -> (string)

  

  This field is deprecated.

  

  

LatestNotificationAttemptSucceeded -> (string)

  

  This field is deprecated.

  

  

LatestDeliveryAttemptSucceeded -> (string)

  

  This field is deprecated.

  

  

TimeLoggingStarted -> (string)

  

  This field is deprecated.

  

  

TimeLoggingStopped -> (string)

  

  This field is deprecated.

  

  

