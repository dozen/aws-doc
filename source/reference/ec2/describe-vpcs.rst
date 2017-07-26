[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-vpcs:


*************
describe-vpcs
*************



===========
Description
===========



Describes one or more of your VPCs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeVpcs>`_


========
Synopsis
========

::

    describe-vpcs
  [--filters <value>]
  [--vpc-ids <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``cidr`` - The IPv4 CIDR block of the VPC. The CIDR block you specify must exactly match the VPC's CIDR block for information to be returned for the VPC. Must contain the slash followed by one or two digits (for example, ``/28`` ). 
   
  * ``dhcp-options-id`` - The ID of a set of DHCP options. 
   
  * ``ipv6-cidr-block-association.ipv6-cidr-block`` - An IPv6 CIDR block associated with the VPC. 
   
  * ``ipv6-cidr-block-association.association-id`` - The association ID for an IPv6 CIDR block associated with the VPC. 
   
  * ``ipv6-cidr-block-association.state`` - The state of an IPv6 CIDR block associated with the VPC. 
   
  * ``isDefault`` - Indicates whether the VPC is the default VPC. 
   
  * ``state`` - The state of the VPC (``pending`` | ``available`` ). 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``vpc-id`` - The ID of the VPC. 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--vpc-ids`` (list)


  One or more VPC IDs.

   

  Default: Describes all your VPCs.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your VPCs**

This example describes your VPCs.

Command::

  aws ec2 describe-vpcs

Output::

  {
      "Vpcs": [
          {
              "VpcId": "vpc-a01106c2",
              "InstanceTenancy": "default",
              "Tags": [
                  {
                      "Value": "MyVPC",
                      "Key": "Name"
                  }
              ],
              "State": "available",
              "DhcpOptionsId": "dopt-7a8b9c2d",
              "CidrBlock": "10.0.0.0/16",
              "IsDefault": false
          },
          {
              "VpcId": "vpc-b61106d4",
              "InstanceTenancy": "dedicated",
              "State": "available",
              "DhcpOptionsId": "dopt-97eb5efa",
              "CidrBlock": "10.50.0.0/16",
              "IsDefault": false
          },
          {
            "VpcId": "vpc-a45db1c0", 
            "InstanceTenancy": "default", 
            "Ipv6CidrBlockAssociationSet": [
                {
                    "Ipv6CidrBlock": "2001:db8:1234:8800::/56", 
                    "AssociationId": "vpc-cidr-assoc-e5a5408c", 
                    "Ipv6CidrBlockState": {
                        "State": "ASSOCIATED"
                    }
                }
            ], 
            "State": "available", 
            "DhcpOptionsId": "dopt-dbedadb2", 
            "CidrBlock": "198.168.0.0/24", 
            "IsDefault": false
        }
      ]  
  }
  
**To describe a specific VPC**

This example describes the specified VPC.

Command::

  aws ec2 describe-vpcs --vpc-ids vpc-a01106c2

Output::

  {
      "Vpcs": [
          {
              "VpcId": "vpc-a01106c2",
              "InstanceTenancy": "default",
              "Tags": [
                  {
                      "Value": "MyVPC",
                      "Key": "Name"
                  }
              ],
              "State": "available",
              "DhcpOptionsId": "dopt-7a8b9c2d",
              "CidrBlock": "10.0.0.0/16",
              "IsDefault": false
          }
      ]  
  }

======
Output
======

Vpcs -> (list)

  

  Information about one or more VPCs.

  

  (structure)

    

    Describes a VPC.

    

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

          

          

        

      

    

  

