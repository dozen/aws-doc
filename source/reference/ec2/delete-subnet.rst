[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-subnet:


*************
delete-subnet
*************



===========
Description
===========



Deletes the specified subnet. You must terminate all running instances in the subnet before you can delete the subnet.



========
Synopsis
========

::

    delete-subnet
  [--dry-run | --no-dry-run]
  --subnet-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--subnet-id`` (string)


  The ID of the subnet.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a subnet**

This example deletes the specified subnet. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-subnet --subnet-id subnet-9d4a7b6c


======
Output
======

None