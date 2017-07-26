[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs get-queue-url:


*************
get-queue-url
*************



===========
Description
===========



Returns the URL of an existing queue. This action provides a simple way to retrieve the URL of an Amazon SQS queue.

 

To access a queue that belongs to another AWS account, use the ``QueueOwnerAWSAccountId`` parameter to specify the account ID of the queue's owner. The queue's owner must grant you permission to access the queue. For more information about shared queue access, see ``  add-permission `` or see `Shared Queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/acp-overview.html>`_ in the *Amazon SQS Developer Guide* . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/GetQueueUrl>`_


========
Synopsis
========

::

    get-queue-url
  --queue-name <value>
  [--queue-owner-aws-account-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-name`` (string)


  The name of the queue whose URL must be fetched. Maximum 80 characters. Valid values: alphanumeric characters, hyphens (``-`` ), and underscores (``_`` ).

   

  Queue names are case-sensitive.

  

``--queue-owner-aws-account-id`` (string)


  The AWS account ID of the account that created the queue.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get a queue URL**

This example gets the specified queue's URL.

Command::

  aws sqs get-queue-url --queue-name MyQueue

Output::

  {
    "QueueUrl": "https://queue.amazonaws.com/80398EXAMPLE/MyQueue"
  }

======
Output
======

QueueUrl -> (string)

  

  The URL of the queue.

  

  

