[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 replace-network-acl-association:


*******************************
replace-network-acl-association
*******************************



===========
Description
===========



Changes which network ACL a subnet is associated with. By default when you create a subnet, it's automatically associated with the default network ACL. For more information about network ACLs, see `Network ACLs <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ReplaceNetworkAclAssociation>`_


========
Synopsis
========

::

    replace-network-acl-association
  --association-id <value>
  [--dry-run | --no-dry-run]
  --network-acl-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--association-id`` (string)


  The ID of the current association between the original network ACL and the subnet.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--network-acl-id`` (string)


  The ID of the new network ACL to associate with the subnet.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

