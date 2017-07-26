[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 cancel-import-task:


******************
cancel-import-task
******************



===========
Description
===========



Cancels an in-process import virtual machine or import snapshot task.



========
Synopsis
========

::

    cancel-import-task
  [--dry-run | --no-dry-run]
  [--import-task-id <value>]
  [--cancel-reason <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--import-task-id`` (string)


  The ID of the import image or import snapshot task to be canceled.

  

``--cancel-reason`` (string)


  The reason for canceling the task.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ImportTaskId -> (string)

  

  The ID of the task being canceled.

  

  

State -> (string)

  

  The current state of the task being canceled.

  

  

PreviousState -> (string)

  

  The current state of the task being canceled.

  

  

