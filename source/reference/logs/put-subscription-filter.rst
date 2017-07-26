[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs put-subscription-filter:


***********************
put-subscription-filter
***********************



===========
Description
===========



Creates or updates a subscription filter and associates it with the specified log group. Subscription filters allow you to subscribe to a real-time stream of log events ingested through  put-log-events and have them delivered to a specific destination. Currently, the supported destinations are:

 

 
* An Amazon Kinesis stream belonging to the same account as the subscription filter, for same-account delivery. 
 
* A logical destination that belongs to a different account, for cross-account delivery. 
 
* An Amazon Kinesis Firehose stream that belongs to the same account as the subscription filter, for same-account delivery. 
 
* An AWS Lambda function that belongs to the same account as the subscription filter, for same-account delivery. 
 

 

There can only be one subscription filter associated with a log group. If you are updating an existing filter, you must specify the correct name in ``filterName`` . Otherwise, the call will fail because you cannot associate a second filter with a log group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/PutSubscriptionFilter>`_


========
Synopsis
========

::

    put-subscription-filter
  --log-group-name <value>
  --filter-name <value>
  --filter-pattern <value>
  --destination-arn <value>
  [--role-arn <value>]
  [--distribution <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group.

  

``--filter-name`` (string)


  A name for the subscription filter. If you are updating an existing filter, you must specify the correct name in ``filterName`` . Otherwise, the call will fail because you cannot associate a second filter with a log group. To find the name of the filter currently associated with a log group, use  describe-subscription-filters .

  

``--filter-pattern`` (string)


  A filter pattern for subscribing to a filtered stream of log events.

  

``--destination-arn`` (string)


  The ARN of the destination to deliver matching log events to. Currently, the supported destinations are:

   

   
  * An Amazon Kinesis stream belonging to the same account as the subscription filter, for same-account delivery. 
   
  * A logical destination (specified using an ARN) belonging to a different account, for cross-account delivery. 
   
  * An Amazon Kinesis Firehose stream belonging to the same account as the subscription filter, for same-account delivery. 
   
  * An AWS Lambda function belonging to the same account as the subscription filter, for same-account delivery. 
   

  

``--role-arn`` (string)


  The ARN of an IAM role that grants CloudWatch Logs permissions to deliver ingested log events to the destination stream. You don't need to provide the ARN when you are working with a logical destination for cross-account delivery.

  

``--distribution`` (string)


  The method used to distribute log data to the destination, when the destination is an Amazon Kinesis stream. By default, log data is grouped by log stream. For a more even distribution, you can group log data randomly.

  

  Possible values:

  
  *   ``Random``

  
  *   ``ByLogStream``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None