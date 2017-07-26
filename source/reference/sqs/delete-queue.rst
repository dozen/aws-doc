[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs delete-queue:


************
delete-queue
************



===========
Description
===========



Deletes the queue specified by the **queue URL** , regardless of whether the queue is empty. If the specified queue does not exist, Amazon SQS returns a successful response. 

 

.. warning::

   

  Use ``delete-queue`` with care; once you delete your queue, any messages in the queue are no longer available. 

   

 

When you delete a queue, the deletion process takes up to 60 seconds. Requests you send involving that queue during the 60 seconds might succeed. For example, a  send-message request might succeed, but after the 60 seconds, the queue and that message you sent no longer exist. Also, when you delete a queue, you must wait at least 60 seconds before creating a queue with the same name. 

 

We reserve the right to delete queues that have had no activity for more than 30 days. For more information, see `How Amazon SQS Queues Work`_ in the *Amazon SQS Developer Guide* . 



========
Synopsis
========

::

    delete-queue
  --queue-url <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to take action on.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a queue**

This example deletes the specified queue.

Command::

  aws sqs delete-queue --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyNewerQueue

Output::

  None.

======
Output
======

None

.. _How Amazon SQS Queues Work: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSConcepts.html
