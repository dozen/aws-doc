[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs remove-permission:


*****************
remove-permission
*****************



===========
Description
===========



Revokes any permissions in the queue policy that matches the specified ``Label`` parameter. Only the owner of the queue can remove permissions.



========
Synopsis
========

::

    remove-permission
  --queue-url <value>
  --label <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to take action on.

  

``--label`` (string)


  The identification of the permission to remove. This is the label added with the  add-permission action.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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