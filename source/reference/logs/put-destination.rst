[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs put-destination:


***************
put-destination
***************



===========
Description
===========



Creates or updates a destination. A destination encapsulates a physical resource (such as a Kinesis stream) and enables you to subscribe to a real-time stream of log events of a different account, ingested using  put-log-events . Currently, the only supported physical resource is a Amazon Kinesis stream belonging to the same account as the destination.

 

A destination controls what is written to its Amazon Kinesis stream through an access policy. By default, ``put-destination`` does not set any access policy with the destination, which means a cross-account user cannot call  put-subscription-filter against this destination. To enable this, the destination owner must call  put-destination-policy after ``put-destination`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/PutDestination>`_


========
Synopsis
========

::

    put-destination
  --destination-name <value>
  --target-arn <value>
  --role-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--destination-name`` (string)


  A name for the destination.

  

``--target-arn`` (string)


  The ARN of an Amazon Kinesis stream to deliver matching log events to.

  

``--role-arn`` (string)


  The ARN of an IAM role that grants CloudWatch Logs permissions to call Amazon Kinesis PutRecord on the destination stream.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

destination -> (structure)

  

  The destination.

  

  destinationName -> (string)

    

    The name of the destination.

    

    

  targetArn -> (string)

    

    The Amazon Resource Name (ARN) of the physical target where the log events will be delivered (for example, a Kinesis stream).

    

    

  roleArn -> (string)

    

    A role for impersonation, used when delivering log events to the target.

    

    

  accessPolicy -> (string)

    

    An IAM policy document that governs which AWS accounts can create subscription filters against this destination.

    

    

  arn -> (string)

    

    The ARN of this destination.

    

    

  creationTime -> (long)

    

    The creation time of the destination, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

    

    

  

