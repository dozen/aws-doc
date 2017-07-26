[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 cancel-conversion-task:


**********************
cancel-conversion-task
**********************



===========
Description
===========



Cancels an active conversion task. The task can be the import of an instance or volume. The action removes all artifacts of the conversion, including a partially uploaded volume or instance. If the conversion is complete or is in the process of transferring the final disk image, the command fails and returns an exception.

 

For more information, see `Using the Command Line Tools to Import Your Virtual Machine to Amazon EC2`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    cancel-conversion-task
  [--dry-run | --no-dry-run]
  --conversion-task-id <value>
  [--reason-message <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--conversion-task-id`` (string)


  The ID of the conversion task.

  

``--reason-message`` (string)


  The reason for canceling the conversion task.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

.. _Using the Command Line Tools to Import Your Virtual Machine to Amazon EC2: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/UploadingYourInstancesandVolumes.html
