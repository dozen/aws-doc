[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 associate-subnet-cidr-block:


***************************
associate-subnet-cidr-block
***************************



===========
Description
===========



Associates a CIDR block with your subnet. You can only associate a single IPv6 CIDR block with your subnet. An IPv6 CIDR block must have a prefix length of /64.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AssociateSubnetCidrBlock>`_


========
Synopsis
========

::

    associate-subnet-cidr-block
  --ipv6-cidr-block <value>
  --subnet-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ipv6-cidr-block`` (string)


  The IPv6 CIDR block for your subnet. The subnet must have a /64 prefix length.

  

``--subnet-id`` (string)


  The ID of your subnet.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To associate an IPv6 CIDR block with a subnet**

This example associates an IPv6 CIDR block with the specified subnet.

Command::

  aws ec2 associate-subnet-cidr-block --subnet-id subnet-5f46ec3b --ipv6-cidr-block 2001:db8:1234:1a00::/64

Output::

  {
    "SubnetId": "subnet-5f46ec3b", 
    "Ipv6CidrBlockAssociation": {
        "Ipv6CidrBlock": "2001:db8:1234:1a00::/64", 
        "AssociationId": "subnet-cidr-assoc-3aa54053", 
        "Ipv6CidrBlockState": {
            "State": "associating"
        }
    }
  }

======
Output
======

Ipv6CidrBlockAssociation -> (structure)

  

  Information about the IPv6 CIDR block association.

  

  AssociationId -> (string)

    

    The association ID for the CIDR block.

    

    

  Ipv6CidrBlock -> (string)

    

    The IPv6 CIDR block.

    

    

  Ipv6CidrBlockState -> (structure)

    

    Information about the state of the CIDR block.

    

    State -> (string)

      

      The state of a CIDR block.

      

      

    StatusMessage -> (string)

      

      A message about the status of the CIDR block, if applicable.

      

      

    

  

SubnetId -> (string)

  

  The ID of the subnet.

  

  

