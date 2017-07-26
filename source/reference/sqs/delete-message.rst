[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs delete-message:


**************
delete-message
**************



===========
Description
===========



Deletes the specified message from the specified queue. You specify the message by using the message's *receipt handle* and not the *MessageId* you receive when you send the message. Even if the message is locked by another reader due to the visibility timeout setting, it is still deleted from the queue. If you leave a message in the queue for longer than the queue's configured retention period, Amazon SQS automatically deletes the message. 

 

.. note::

   

  The receipt handle is associated with a specific instance of receiving the message. If you receive a message more than once, the receipt handle you get each time you receive the message is different. If you don't provide the most recently received receipt handle for the message when you use the ``delete-message`` action, the request succeeds, but the message might not be deleted.

   

  For standard queues, it is possible to receive a message even after you delete it. This might happen on rare occasions if one of the servers storing a copy of the message is unavailable when you send the request to delete the message. The copy remains on the server and might be returned to you on a subsequent receive request. You should ensure that your application is idempotent, so that receiving a message more than once does not cause issues.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/DeleteMessage>`_


========
Synopsis
========

::

    delete-message
  --queue-url <value>
  --receipt-handle <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue from which messages are deleted.

   

  Queue URLs are case-sensitive.

  

``--receipt-handle`` (string)


  The receipt handle associated with the message to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a message**

This example deletes the specified message.

Command::

  aws sqs delete-message --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue --receipt-handle AQEBRXTo...q2doVA==

Output::

  None.

======
Output
======

None