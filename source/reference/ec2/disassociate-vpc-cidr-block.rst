[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 disassociate-vpc-cidr-block:


***************************
disassociate-vpc-cidr-block
***************************



===========
Description
===========



Disassociates a CIDR block from a VPC. Currently, you can disassociate an IPv6 CIDR block only. You must detach or delete all gateways and resources that are associated with the CIDR block before you can disassociate it. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DisassociateVpcCidrBlock>`_


========
Synopsis
========

::

    disassociate-vpc-cidr-block
  --association-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--association-id`` (string)


  The association ID for the CIDR block.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To disassociate an IPv6 CIDR block from a VPC**

This example disassociates an IPv6 CIDR block from a VPC using the association ID for the CIDR block.

Command::

  aws ec2 disassociate-vpc-cidr-block --association-id vpc-cidr-assoc-eca54085

Output::

  {
    "Ipv6CidrBlockAssociation": {
        "Ipv6CidrBlock": "2001:db8:1234:1a00::/56", 
        "AssociationId": "vpc-cidr-assoc-eca54085", 
        "Ipv6CidrBlockState": {
            "State": "disassociating"
        }
    }, 
    "VpcId": "vpc-a034d6c4"
  }

======
Output
======

Ipv6CidrBlockAssociation -> (structure)

  

  Information about the IPv6 CIDR block association.

  

  AssociationId -> (string)

    

    The association ID for the IPv6 CIDR block.

    

    

  Ipv6CidrBlock -> (string)

    

    The IPv6 CIDR block.

    

    

  Ipv6CidrBlockState -> (structure)

    

    Information about the state of the CIDR block.

    

    State -> (string)

      

      The state of the CIDR block.

      

      

    StatusMessage -> (string)

      

      A message about the status of the CIDR block, if applicable.

      

      

    

  

VpcId -> (string)

  

  The ID of the VPC.

  

  

