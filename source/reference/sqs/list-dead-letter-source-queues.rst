[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs list-dead-letter-source-queues:


******************************
list-dead-letter-source-queues
******************************



===========
Description
===========



Returns a list of your queues that have the ``RedrivePolicy`` queue attribute configured with a dead letter queue.

 

For more information about using dead letter queues, see `Using Amazon SQS Dead Letter Queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html>`_ in the *Amazon SQS Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/ListDeadLetterSourceQueues>`_


========
Synopsis
========

::

    list-dead-letter-source-queues
  --queue-url <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of a dead letter queue.

   

  Queue URLs are case-sensitive.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list dead letter source queues**

This example lists the queues that are associated with the specified dead letter source queue.

Command::

  aws sqs list-dead-letter-source-queues --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyDeadLetterQueue

Output::

  {
    "queueUrls": [
      "https://queue.amazonaws.com/80398EXAMPLE/MyQueue",
      "https://queue.amazonaws.com/80398EXAMPLE/MyOtherQueue"
    ]
  }

======
Output
======

queueUrls -> (list)

  

  A list of source queue URLs that have the ``RedrivePolicy`` queue attribute configured with a dead letter queue.

  

  (string)

    

    

  

