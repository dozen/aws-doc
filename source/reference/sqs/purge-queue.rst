[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs purge-queue:


***********
purge-queue
***********



===========
Description
===========



Deletes the messages in a queue specified by the **queue URL** .

 

.. warning::

  When you use the ``purge-queue`` API, the deleted messages in the queue cannot be retrieved.

 

When you purge a queue, the message deletion process takes up to 60 seconds. All messages sent to the queue before calling ``purge-queue`` will be deleted; messages sent to the queue while it is being purged may be deleted. While the queue is being purged, messages sent to the queue before ``purge-queue`` was called may be received, but will be deleted within the next minute.



========
Synopsis
========

::

    purge-queue
  --queue-url <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-url`` (string)


  The queue URL of the queue to delete the messages from when using the ``purge-queue`` API.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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