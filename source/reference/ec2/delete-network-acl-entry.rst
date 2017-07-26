[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-network-acl-entry:


************************
delete-network-acl-entry
************************



===========
Description
===========



Deletes the specified ingress or egress entry (rule) from the specified network ACL.



========
Synopsis
========

::

    delete-network-acl-entry
  [--dry-run | --no-dry-run]
  --network-acl-id <value>
  --rule-number <value>
  --egress | --ingress
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--network-acl-id`` (string)


  The ID of the network ACL.

  

``--rule-number`` (integer)


  The rule number of the entry to delete.

  

``--egress`` | ``--ingress`` (boolean)


  Indicates whether the rule is an egress rule.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a network ACL entry**

This example deletes ingress rule number 100 from the specified network ACL. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-network-acl-entry --network-acl-id acl-5fb85d36 --ingress --rule-number 100


======
Output
======

None