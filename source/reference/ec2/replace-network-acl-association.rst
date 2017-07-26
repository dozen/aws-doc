[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 replace-network-acl-association:


*******************************
replace-network-acl-association
*******************************



===========
Description
===========



Changes which network ACL a subnet is associated with. By default when you create a subnet, it's automatically associated with the default network ACL. For more information about network ACLs, see `Network ACLs`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    replace-network-acl-association
  [--dry-run | --no-dry-run]
  --association-id <value>
  --network-acl-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--association-id`` (string)


  The ID of the current association between the original network ACL and the subnet.

  

``--network-acl-id`` (string)


  The ID of the new network ACL to associate with the subnet.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To replace the network ACL associated with a subnet**

This example associates the specified network ACL with the subnet for the specified network ACL association.

Command::

  aws ec2 replace-network-acl-association --association-id aclassoc-e5b95c8c --network-acl-id acl-5fb85d36

Output::

  {
      "NewAssociationId": "aclassoc-3999875b"
  }

======
Output
======

NewAssociationId -> (string)

  

  The ID of the new association.

  

  



.. _Network ACLs: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html
