[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs get-queue-url:


*************
get-queue-url
*************



===========
Description
===========



Returns the URL of an existing queue. This action provides a simple way to retrieve the URL of an Amazon SQS queue. 

 

To access a queue that belongs to another AWS account, use the ``QueueOwnerAWSAccountId`` parameter to specify the account ID of the queue's owner. The queue's owner must grant you permission to access the queue. For more information about shared queue access, see  add-permission or go to `Shared Queues`_ in the *Amazon SQS Developer Guide* . 



========
Synopsis
========

::

    get-queue-url
  --queue-name <value>
  [--queue-owner-aws-account-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-name`` (string)


  The name of the queue whose URL must be fetched. Maximum 80 characters; alphanumeric characters, hyphens (-), and underscores (_) are allowed.

  

``--queue-owner-aws-account-id`` (string)


  The AWS account ID of the account that created the queue.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  The URL for the queue.

  

  



.. _Shared Queues: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/acp-overview.html
