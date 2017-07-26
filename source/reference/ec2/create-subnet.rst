[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-subnet:


*************
create-subnet
*************



===========
Description
===========



Creates a subnet in an existing VPC.

 

When you create each subnet, you provide the VPC ID and the CIDR block you want for the subnet. After you create a subnet, you can't change its CIDR block. The subnet's CIDR block can be the same as the VPC's CIDR block (assuming you want only a single subnet in the VPC), or a subset of the VPC's CIDR block. If you create more than one subnet in a VPC, the subnets' CIDR blocks must not overlap. The smallest subnet (and VPC) you can create uses a /28 netmask (16 IP addresses), and the largest uses a /16 netmask (65,536 IP addresses).

 

.. warning::

   

  AWS reserves both the first four and the last IP address in each subnet's CIDR block. They're not available for use.

   

 

If you add more than one subnet to a VPC, they're set up in a star topology with a logical router in the middle.

 

If you launch an instance in a VPC using an Amazon EBS-backed AMI, the IP address doesn't change if you stop and restart the instance (unlike a similar instance launched outside a VPC, which gets a new IP address when restarted). It's therefore possible to have a subnet with no running instances (they're all stopped), but no remaining IP addresses available.

 

For more information about subnets, see `Your VPC and Subnets`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    create-subnet
  [--dry-run | --no-dry-run]
  --vpc-id <value>
  --cidr-block <value>
  [--availability-zone <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-id`` (string)


  The ID of the VPC.

  

``--cidr-block`` (string)


  The network range for the subnet, in CIDR notation. For example, ``10.0.0.0/24`` .

  

``--availability-zone`` (string)


  The Availability Zone for the subnet.

   

  Default: AWS selects one for you. If you create more than one subnet in your VPC, we may not necessarily select a different zone for each subnet. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a subnet**

This example creates a subnet in the specified VPC with the specified CIDR block. We recommend that you let us select an Availability Zone for you. Alternatively, you can use the ``--availability-zone`` option to specify the Availability Zone.

Command::

  aws ec2 create-subnet --vpc-id vpc-a01106c2 --cidr-block 10.0.1.0/24 

Output::

  {
      "Subnet": {
          "VpcId": "vpc-a01106c2",
          "CidrBlock": "10.0.1.0/24",
          "State": "pending",
          "AvailabilityZone": "us-east-1c",
          "SubnetId": "subnet-9d4a7b6c",
          "AvailableIpAddressCount": 251
      }  
  }

======
Output
======

Subnet -> (structure)

  

  Information about the subnet.

  

  SubnetId -> (string)

    

    The ID of the subnet.

    

    

  State -> (string)

    

    The current state of the subnet.

    

    

  VpcId -> (string)

    

    The ID of the VPC the subnet is in.

    

    

  CidrBlock -> (string)

    

    The CIDR block assigned to the subnet.

    

    

  AvailableIpAddressCount -> (integer)

    

    The number of unused IP addresses in the subnet. Note that the IP addresses for any stopped instances are considered unavailable.

    

    

  AvailabilityZone -> (string)

    

    The Availability Zone of the subnet.

    

    

  DefaultForAz -> (boolean)

    

    Indicates whether this is the default subnet for the Availability Zone.

    

    

  MapPublicIpOnLaunch -> (boolean)

    

    Indicates whether instances launched in this subnet receive a public IP address.

    

    

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

        

        

      

    

  



.. _Your VPC and Subnets: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Subnets.html
