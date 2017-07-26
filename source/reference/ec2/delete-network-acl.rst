[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-network-acl:


******************
delete-network-acl
******************



===========
Description
===========



Deletes the specified network ACL. You can't delete the ACL if it's associated with any subnets. You can't delete the default network ACL.



========
Synopsis
========

::

    delete-network-acl
  [--dry-run | --no-dry-run]
  --network-acl-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--network-acl-id`` (string)


  The ID of the network ACL.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a network ACL**

This example deletes the specified network ACL. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-network-acl --network-acl-id acl-5fb85d36


======
Output
======

None