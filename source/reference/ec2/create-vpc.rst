[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-vpc:


**********
create-vpc
**********



===========
Description
===========



Creates a VPC with the specified CIDR block.

 

The smallest VPC you can create uses a /28 netmask (16 IP addresses), and the largest uses a /16 netmask (65,536 IP addresses). To help you decide how big to make your VPC, see `Your VPC and Subnets`_ in the *Amazon Virtual Private Cloud User Guide* .

 

By default, each instance you launch in the VPC has the default DHCP options, which includes only a default DNS server that we provide (AmazonProvidedDNS). For more information about DHCP options, see `DHCP Options Sets`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    create-vpc
  [--dry-run | --no-dry-run]
  --cidr-block <value>
  [--instance-tenancy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cidr-block`` (string)


  The network range for the VPC, in CIDR notation. For example, ``10.0.0.0/16`` .

  

``--instance-tenancy`` (string)


  The supported tenancy options for instances launched into the VPC. A value of ``default`` means that instances can be launched with any tenancy; a value of ``dedicated`` means all instances launched into the VPC are launched as dedicated tenancy instances regardless of the tenancy assigned to the instance at launch. Dedicated tenancy instances run on single-tenant hardware.

   

  **Important:** The ``host`` value cannot be used with this parameter. Use the ``default`` or ``dedicated`` values only.

   

  Default: ``default`` 

  

  Possible values:

  
  *   ``default``

  
  *   ``dedicated``

  
  *   ``host``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a VPC**

This example creates a VPC with the specified CIDR block.

Command::

  aws ec2 create-vpc --cidr-block 10.0.0.0/16

Output::

  {
      "Vpc": {
          "InstanceTenancy": "default",
          "State": "pending",
          "VpcId": "vpc-a01106c2",
          "CidrBlock": "10.0.0.0/16",
          "DhcpOptionsId": "dopt-7a8b9c2d"
      }
  }
  
**To create a VPC with dedicated tenancy**

This example creates a VPC with the specified CIDR block and ``dedicated`` tenancy.

Command::

  aws ec2 create-vpc --cidr-block 10.0.0.0/16 --instance-tenancy dedicated

Output::

  {
      "Vpc": {
          "InstanceTenancy": "dedicated",
          "State": "pending",
          "VpcId": "vpc-a01106c2",
          "CidrBlock": "10.0.0.0/16",
          "DhcpOptionsId": "dopt-7a8b9c2d"
      }
  }  

======
Output
======

Vpc -> (structure)

  

  Information about the VPC.

  

  VpcId -> (string)

    

    The ID of the VPC.

    

    

  State -> (string)

    

    The current state of the VPC.

    

    

  CidrBlock -> (string)

    

    The CIDR block for the VPC.

    

    

  DhcpOptionsId -> (string)

    

    The ID of the set of DHCP options you've associated with the VPC (or ``default`` if the default options are associated with the VPC).

    

    

  Tags -> (list)

    

    Any tags assigned to the VPC.

    

    (structure)

      

      Describes a tag.

      

      Key -> (string)

        

        The key of the tag. 

         

        Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

        

        

      Value -> (string)

        

        The value of the tag.

         

        Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

        

        

      

    

  InstanceTenancy -> (string)

    

    The allowed tenancy of instances launched into the VPC.

    

    

  IsDefault -> (boolean)

    

    Indicates whether the VPC is the default VPC.

    

    

  



.. _Your VPC and Subnets: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Subnets.html
.. _DHCP Options Sets: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_DHCP_Options.html
