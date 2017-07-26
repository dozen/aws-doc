[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 associate-vpc-cidr-block:


************************
associate-vpc-cidr-block
************************



===========
Description
===========



Associates a CIDR block with your VPC. You can only associate a single Amazon-provided IPv6 CIDR block with your VPC. The IPv6 CIDR block size is fixed at /56.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AssociateVpcCidrBlock>`_


========
Synopsis
========

::

    associate-vpc-cidr-block
  [--amazon-provided-ipv6-cidr-block | --no-amazon-provided-ipv6-cidr-block]
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--amazon-provided-ipv6-cidr-block`` | ``--no-amazon-provided-ipv6-cidr-block`` (boolean)


  Requests an Amazon-provided IPv6 CIDR block with a /56 prefix length for the VPC. You cannot specify the range of IPv6 addresses, or the size of the CIDR block.

  

``--vpc-id`` (string)


  The ID of the VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To associate an IPv6 CIDR block with a VPC**

This example associates an IPv6 CIDR block with a VPC.

Command::

  aws ec2 associate-vpc-cidr-block --amazon-provided-ipv6-cidr-block --vpc-id vpc-a034d6c4

Output::

  {
    "Ipv6CidrBlockAssociation": {
        "Ipv6CidrBlockState": {
            "State": "associating"
        }, 
        "AssociationId": "vpc-cidr-assoc-eca54085"
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

  

  

