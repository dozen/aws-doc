[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs list-dead-letter-source-queues:


******************************
list-dead-letter-source-queues
******************************



===========
Description
===========



Returns a list of your queues that have the RedrivePolicy queue attribute configured with a dead letter queue.

 

For more information about using dead letter queues, see `Using Amazon SQS Dead Letter Queues`_ .



========
Synopsis
========

::

    list-dead-letter-source-queues
  --queue-url <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-url`` (string)
The queue URL of a dead letter queue.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  A list of source queue URLs that have the RedrivePolicy queue attribute configured with a dead letter queue.

  (string)

    

    

  



.. _Using Amazon SQS Dead Letter Queues: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSDeadLetterQueue.html
