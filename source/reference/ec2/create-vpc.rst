[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-vpc:


**********
create-vpc
**********



===========
Description
===========



Creates a VPC with the specified IPv4 CIDR block. The smallest VPC you can create uses a /28 netmask (16 IPv4 addresses), and the largest uses a /16 netmask (65,536 IPv4 addresses). To help you decide how big to make your VPC, see `Your VPC and Subnets <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Subnets.html>`_ in the *Amazon Virtual Private Cloud User Guide* .

 

You can optionally request an Amazon-provided IPv6 CIDR block for the VPC. The IPv6 CIDR block uses a /56 prefix length, and is allocated from Amazon's pool of IPv6 addresses. You cannot choose the IPv6 range for your VPC.

 

By default, each instance you launch in the VPC has the default DHCP options, which includes only a default DNS server that we provide (AmazonProvidedDNS). For more information about DHCP options, see `DHCP Options Sets <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_DHCP_Options.html>`_ in the *Amazon Virtual Private Cloud User Guide* .

 

You can specify the instance tenancy value for the VPC when you create it. You can't change this value for the VPC after you create it. For more information, see `Dedicated Instances <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/dedicated-instance.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateVpc>`_


========
Synopsis
========

::

    create-vpc
  --cidr-block <value>
  [--amazon-provided-ipv6-cidr-block | --no-amazon-provided-ipv6-cidr-block]
  [--dry-run | --no-dry-run]
  [--instance-tenancy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cidr-block`` (string)


  The IPv4 network range for the VPC, in CIDR notation. For example, ``10.0.0.0/16`` .

  

``--amazon-provided-ipv6-cidr-block`` | ``--no-amazon-provided-ipv6-cidr-block`` (boolean)


  Requests an Amazon-provided IPv6 CIDR block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or the size of the CIDR block.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-tenancy`` (string)


  The tenancy options for instances launched into the VPC. For ``default`` , instances are launched with shared tenancy by default. You can launch instances with any tenancy into a shared tenancy VPC. For ``dedicated`` , instances are launched as dedicated tenancy instances by default. You can only launch instances with a tenancy of ``dedicated`` or ``host`` into a dedicated tenancy VPC. 

   

   **Important:** The ``host`` value cannot be used with this parameter. Use the ``default`` or ``dedicated`` values only.

   

  Default: ``default``  

  

  Possible values:

  
  *   ``default``

  
  *   ``dedicated``

  
  *   ``host``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a VPC**

This example creates a VPC with the specified IPv4 CIDR block.

Command::

  aws ec2 create-vpc --cidr-block 10.0.0.0/16

Output::

  {
      "Vpc": {
        "VpcId": "vpc-145db170", 
        "InstanceTenancy": "default", 
        "CidrBlockAssociationSet": [], 
        "Ipv6CidrBlockAssociationSet": [], 
        "State": "pending", 
        "DhcpOptionsId": "dopt-dbedadb2", 
        "CidrBlock": "10.0.0.0/16", 
        "IsDefault": false
      }
  }
  
**To create a VPC with dedicated tenancy**

This example creates a VPC with the specified IPv4 CIDR block and ``dedicated`` tenancy.

Command::

  aws ec2 create-vpc --cidr-block 10.0.0.0/16 --instance-tenancy dedicated

Output::

  {
      "Vpc": {
        "VpcId": "vpc-145db170", 
        "InstanceTenancy": "dedicated", 
        "CidrBlockAssociationSet": [], 
        "Ipv6CidrBlockAssociationSet": [], 
        "State": "pending", 
        "DhcpOptionsId": "dopt-dbedadb2", 
        "CidrBlock": "10.0.0.0/16", 
        "IsDefault": false
      }
  }  
  
**To create a VPC with an IPv6 CIDR block**

This example creates a VPC with an Amazon-provided IPv6 CIDR block.

Command::

  aws ec2 create-vpc --cidr-block 10.0.0.0/16 --amazon-provided-ipv6-cidr-block
  
Output::

  {
    "Vpc": {
        "VpcId": "vpc-31896b55", 
        "InstanceTenancy": "default", 
        "CidrBlockAssociationSet": [], 
        "Ipv6CidrBlockAssociationSet": [
            {
                "Ipv6CidrBlock": "", 
                "AssociationId": "vpc-cidr-assoc-17a5407e", 
                "Ipv6CidrBlockState": {
                    "State": "associating"
                }
            }
        ], 
        "State": "pending", 
        "DhcpOptionsId": "dopt-dbedadb2", 
        "CidrBlock": "10.0.0.0/16", 
        "IsDefault": false
    }
  }


======
Output
======

Vpc -> (structure)

  

  Information about the VPC.

  

  CidrBlock -> (string)

    

    The IPv4 CIDR block for the VPC.

    

    

  DhcpOptionsId -> (string)

    

    The ID of the set of DHCP options you've associated with the VPC (or ``default`` if the default options are associated with the VPC).

    

    

  State -> (string)

    

    The current state of the VPC.

    

    

  VpcId -> (string)

    

    The ID of the VPC.

    

    

  InstanceTenancy -> (string)

    

    The allowed tenancy of instances launched into the VPC.

    

    

  Ipv6CidrBlockAssociationSet -> (list)

    

    Information about the IPv6 CIDR blocks associated with the VPC.

    

    (structure)

      

      Describes an IPv6 CIDR block associated with a VPC.

      

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

          

          

        

      

    

  IsDefault -> (boolean)

    

    Indicates whether the VPC is the default VPC.

    

    

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

        

        

      

    

  

