[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs purge-queue:


***********
purge-queue
***********



===========
Description
===========



Deletes the messages in a queue specified by the ``QueueURL`` parameter.

 

.. warning::

   

  When you use the ``purge-queue`` action, you can't retrieve a message deleted from a queue.

   

 

When you purge a queue, the message deletion process takes up to 60 seconds. All messages sent to the queue before calling the ``purge-queue`` action are deleted. Messages sent to the queue while it is being purged might be deleted. While the queue is being purged, messages sent to the queue before ``purge-queue`` is called might be received, but are deleted within the next minute.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/PurgeQueue>`_


========
Synopsis
========

::

    purge-queue
  --queue-url <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of the queue from which the ``purge-queue`` action deletes messages.

   

  Queue URLs are case-sensitive.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To purge a queue**

This example deletes all messages in the specified queue.

Command::

  aws sqs purge-queue --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyNewQueue

Output::

  None.

======
Output
======

None