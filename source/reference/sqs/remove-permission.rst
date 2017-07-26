[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs remove-permission:


*****************
remove-permission
*****************



===========
Description
===========



Revokes any permissions in the queue policy that matches the specified ``Label`` parameter. Only the owner of the queue can remove permissions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/RemovePermission>`_


========
Synopsis
========

::

    remove-permission
  --queue-url <value>
  --label <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue from which permissions are removed.

   

  Queue URLs are case-sensitive.

  

``--label`` (string)


  The identification of the permission to remove. This is the label added using the ``  add-permission `` action.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To remove a permission**

This example removes the permission with the specified label from the specified queue.

Command::

  aws sqs remove-permission --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue --label SendMessagesFromMyQueue

Output::

  None.

======
Output
======

None