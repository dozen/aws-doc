[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 deregister-image:


****************
deregister-image
****************



===========
Description
===========



Deregisters the specified AMI. After you deregister an AMI, it can't be used to launch new instances.

 

This command does not delete the AMI.



========
Synopsis
========

::

    deregister-image
  [--dry-run | --no-dry-run]
  --image-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--image-id`` (string)


  The ID of the AMI.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To deregister an AMI**

This example deregisters the specified AMI. If the command succeeds, no output is returned.

Command::

  aws ec2 deregister-image --image-id ami-4fa54026


======
Output
======

None