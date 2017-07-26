[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-subnet:


*************
create-subnet
*************



===========
Description
===========



Creates a subnet in an existing VPC.

 

When you create each subnet, you provide the VPC ID and the CIDR block you want for the subnet. After you create a subnet, you can't change its CIDR block. The subnet's IPv4 CIDR block can be the same as the VPC's IPv4 CIDR block (assuming you want only a single subnet in the VPC), or a subset of the VPC's IPv4 CIDR block. If you create more than one subnet in a VPC, the subnets' CIDR blocks must not overlap. The smallest IPv4 subnet (and VPC) you can create uses a /28 netmask (16 IPv4 addresses), and the largest uses a /16 netmask (65,536 IPv4 addresses).

 

If you've associated an IPv6 CIDR block with your VPC, you can create a subnet with an IPv6 CIDR block that uses a /64 prefix length. 

 

.. warning::

   

  AWS reserves both the first four and the last IPv4 address in each subnet's CIDR block. They're not available for use.

   

 

If you add more than one subnet to a VPC, they're set up in a star topology with a logical router in the middle.

 

If you launch an instance in a VPC using an Amazon EBS-backed AMI, the IP address doesn't change if you stop and restart the instance (unlike a similar instance launched outside a VPC, which gets a new IP address when restarted). It's therefore possible to have a subnet with no running instances (they're all stopped), but no remaining IP addresses available.

 

For more information about subnets, see `Your VPC and Subnets <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Subnets.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateSubnet>`_


========
Synopsis
========

::

    create-subnet
  [--availability-zone <value>]
  --cidr-block <value>
  [--ipv6-cidr-block <value>]
  --vpc-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--availability-zone`` (string)


  The Availability Zone for the subnet.

   

  Default: AWS selects one for you. If you create more than one subnet in your VPC, we may not necessarily select a different zone for each subnet.

  

``--cidr-block`` (string)


  The IPv4 network range for the subnet, in CIDR notation. For example, ``10.0.0.0/24`` .

  

``--ipv6-cidr-block`` (string)


  The IPv6 network range for the subnet, in CIDR notation. The subnet size must use a /64 prefix length.

  

``--vpc-id`` (string)


  The ID of the VPC.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a subnet**

This example creates a subnet in the specified VPC with the specified IPv4 CIDR block. We recommend that you let us select an Availability Zone for you. Alternatively, you can use the ``--availability-zone`` option to specify the Availability Zone.

Command::

  aws ec2 create-subnet --vpc-id vpc-a01106c2 --cidr-block 10.0.1.0/24 

Output::

  {
      "Subnet": {
        "VpcId": "vpc-a01106c2",
        "AvailableIpAddressCount": 251, 
        "MapPublicIpOnLaunch": false, 
        "DefaultForAz": false, 
        "Ipv6CidrBlockAssociationSet": [], 
        "State": "pending", 
        "AvailabilityZone": "us-east-1a", 
        "SubnetId": "subnet-2c2de375", 
        "CidrBlock": "10.0.1.0/24", 
        "AssignIpv6AddressOnCreation": false
      }  
  }

**To create a subnet with an IPv6 CIDR block**

This example creates a subnet in the specified VPC with the specified IPv4 and IPv6 CIDR blocks (from the ranges of the VPC).

Command::

  aws ec2 create-subnet --vpc-id vpc-31896b55 --cidr-block 10.0.0.0/24 --ipv6-cidr-block 2001:db8:1234:a100::/64
  
Output::

  {
    "Subnet": {
        "VpcId": "vpc-31896b55", 
        "AvailableIpAddressCount": 251, 
        "MapPublicIpOnLaunch": false, 
        "DefaultForAz": false, 
        "Ipv6CidrBlockAssociationSet": [
            {
                "Ipv6CidrBlock": "2001:db8:1234:a100::/64", 
                "AssociationId": "subnet-cidr-assoc-3fe7e347", 
                "Ipv6CidrBlockState": {
                    "State": "ASSOCIATING"
                }
            }
        ], 
        "State": "pending", 
        "AvailabilityZone": "ap-southeast-2a", 
        "SubnetId": "subnet-5504d223", 
        "CidrBlock": "10.0.0.0/24", 
        "AssignIpv6AddressOnCreation": false
    }
  }

======
Output
======

Subnet -> (structure)

  

  Information about the subnet.

  

  AvailabilityZone -> (string)

    

    The Availability Zone of the subnet.

    

    

  AvailableIpAddressCount -> (integer)

    

    The number of unused private IPv4 addresses in the subnet. Note that the IPv4 addresses for any stopped instances are considered unavailable.

    

    

  CidrBlock -> (string)

    

    The IPv4 CIDR block assigned to the subnet.

    

    

  DefaultForAz -> (boolean)

    

    Indicates whether this is the default subnet for the Availability Zone.

    

    

  MapPublicIpOnLaunch -> (boolean)

    

    Indicates whether instances launched in this subnet receive a public IPv4 address.

    

    

  State -> (string)

    

    The current state of the subnet.

    

    

  SubnetId -> (string)

    

    The ID of the subnet.

    

    

  VpcId -> (string)

    

    The ID of the VPC the subnet is in.

    

    

  AssignIpv6AddressOnCreation -> (boolean)

    

    Indicates whether a network interface created in this subnet (including a network interface created by  run-instances ) receives an IPv6 address.

    

    

  Ipv6CidrBlockAssociationSet -> (list)

    

    Information about the IPv6 CIDR blocks associated with the subnet.

    

    (structure)

      

      Describes an IPv6 CIDR block associated with a subnet.

      

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

          

          

        

      

    

  Tags -> (list)

    

    Any tags assigned to the subnet.

    

    (structure)

      

      Describes a tag.

      

      Key -> (string)

        

        The key of the tag.

         

        Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

        

        

      Value -> (string)

        

        The value of the tag.

         

        Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

        

        

      

    

  

