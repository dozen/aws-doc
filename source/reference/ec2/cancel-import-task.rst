[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 cancel-import-task:


******************
cancel-import-task
******************



===========
Description
===========



Cancels an in-process import virtual machine or import snapshot task.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CancelImportTask>`_


========
Synopsis
========

::

    cancel-import-task
  [--cancel-reason <value>]
  [--dry-run | --no-dry-run]
  [--import-task-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cancel-reason`` (string)


  The reason for canceling the task.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--import-task-id`` (string)


  The ID of the import image or import snapshot task to be canceled.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ImportTaskId -> (string)

  

  The ID of the task being canceled.

  

  

PreviousState -> (string)

  

  The current state of the task being canceled.

  

  

State -> (string)

  

  The current state of the task being canceled.

  

  

