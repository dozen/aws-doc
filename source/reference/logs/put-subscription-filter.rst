[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs put-subscription-filter:


***********************
put-subscription-filter
***********************



===========
Description
===========



Creates or updates a subscription filter and associates it with the specified log group. Subscription filters allow you to subscribe to a real-time stream of log events ingested through ``put-log-events`` requests and have them delivered to a specific destination. Currently, the supported destinations are: 

 
* An Amazon Kinesis stream belonging to the same account as the subscription filter, for same-account delivery. 
 
* A logical destination (used via an ARN of ``Destination`` ) belonging to a different account, for cross-account delivery. 
 
* An Amazon Kinesis Firehose stream belonging to the same account as the subscription filter, for same-account delivery. 
 
* An AWS Lambda function belonging to the same account as the subscription filter, for same-account delivery. 
 

 

 

Currently there can only be one subscription filter associated with a log group. 



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
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group to associate the subscription filter with.

  

``--filter-name`` (string)


  A name for the subscription filter.

  

``--filter-pattern`` (string)


  A valid CloudWatch Logs filter pattern for subscribing to a filtered stream of log events.

  

``--destination-arn`` (string)


  The ARN of the destination to deliver matching log events to. Currently, the supported destinations are: 

   
  * An Amazon Kinesis stream belonging to the same account as the subscription filter, for same-account delivery. 
   
  * A logical destination (used via an ARN of ``Destination`` ) belonging to a different account, for cross-account delivery. 
   
  * An Amazon Kinesis Firehose stream belonging to the same account as the subscription filter, for same-account delivery. 
   
  * An AWS Lambda function belonging to the same account as the subscription filter, for same-account delivery. 
   

   

  

``--role-arn`` (string)


  The ARN of an IAM role that grants CloudWatch Logs permissions to deliver ingested log events to the destination stream. You don't need to provide the ARN when you are working with a logical destination (used via an ARN of ``Destination`` ) for cross-account delivery.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None