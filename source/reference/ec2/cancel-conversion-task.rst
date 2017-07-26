[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 cancel-conversion-task:


**********************
cancel-conversion-task
**********************



===========
Description
===========



Cancels an active conversion task. The task can be the import of an instance or volume. The action removes all artifacts of the conversion, including a partially uploaded volume or instance. If the conversion is complete or is in the process of transferring the final disk image, the command fails and returns an exception.

 

For more information, see `Importing a Virtual Machine Using the Amazon EC2 CLI <http://docs.aws.amazon.com/AWSEC2/latest/CommandLineReference/ec2-cli-vmimport-export.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CancelConversionTask>`_


========
Synopsis
========

::

    cancel-conversion-task
  --conversion-task-id <value>
  [--dry-run | --no-dry-run]
  [--reason-message <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--conversion-task-id`` (string)


  The ID of the conversion task.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--reason-message`` (string)


  The reason for canceling the conversion task.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To cancel an active conversion of an instance or a volume**

This example cancels the upload associated with the task ID import-i-fh95npoc. If the command succeeds, no output is returned.

Command::

  aws ec2 cancel-conversion-task --conversion-task-id import-i-fh95npoc


======
Output
======

None