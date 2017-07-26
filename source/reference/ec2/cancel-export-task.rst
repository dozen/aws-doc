[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 cancel-export-task:


******************
cancel-export-task
******************



===========
Description
===========



Cancels an active export task. The request removes all artifacts of the export, including any partially-created Amazon S3 objects. If the export task is complete or is in the process of transferring the final disk image, the command fails and returns an error.



========
Synopsis
========

::

    cancel-export-task
  --export-task-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--export-task-id`` (string)


  The ID of the export task. This is the ID returned by ``create-instance-export-task`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To cancel an active export task**

This example cancels an active export task with the task ID export-i-fgelt0i7. If the command succeeds, no output is returned.

Command::

  aws ec2 cancel-export-task --export-task-id export-i-fgelt0i7


======
Output
======

None