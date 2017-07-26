[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 cancel-export-task:


******************
cancel-export-task
******************



===========
Description
===========



Cancels an active export task. The request removes all artifacts of the export, including any partially-created Amazon S3 objects. If the export task is complete or is in the process of transferring the final disk image, the command fails and returns an error.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CancelExportTask>`_


========
Synopsis
========

::

    cancel-export-task
  --export-task-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--export-task-id`` (string)


  The ID of the export task. This is the ID returned by ``create-instance-export-task`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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