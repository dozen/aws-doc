[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs delete-queue:


************
delete-queue
************



===========
Description
===========



Deletes the queue specified by the ``QueueUrl`` , even if the queue is empty. If the specified queue doesn't exist, Amazon SQS returns a successful response.

 

.. warning::

   

  Be careful with the ``delete-queue`` action: When you delete a queue, any messages in the queue are no longer available. 

   

 

When you delete a queue, the deletion process takes up to 60 seconds. Requests you send involving that queue during the 60 seconds might succeed. For example, a ``  send-message `` request might succeed, but after 60 seconds the queue and the message you sent no longer exist.

 

When you delete a queue, you must wait at least 60 seconds before creating a queue with the same name. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/DeleteQueue>`_


========
Synopsis
========

::

    delete-queue
  --queue-url <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to delete.

   

  Queue URLs are case-sensitive.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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