[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-subnets:


****************
describe-subnets
****************



===========
Description
===========



Describes one or more of your subnets.

 

For more information about subnets, see `Your VPC and Subnets <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Subnets.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeSubnets>`_


========
Synopsis
========

::

    describe-subnets
  [--filters <value>]
  [--subnet-ids <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``availabilityZone`` - The Availability Zone for the subnet. You can also use ``availability-zone`` as the filter name. 
   
  * ``available-ip-address-count`` - The number of IPv4 addresses in the subnet that are available. 
   
  * ``cidrBlock`` - The IPv4 CIDR block of the subnet. The CIDR block you specify must exactly match the subnet's CIDR block for information to be returned for the subnet. You can also use ``cidr`` or ``cidr-block`` as the filter names. 
   
  * ``defaultForAz`` - Indicates whether this is the default subnet for the Availability Zone. You can also use ``default-for-az`` as the filter name. 
   
  * ``ipv6-cidr-block-association.ipv6-cidr-block`` - An IPv6 CIDR block associated with the subnet. 
   
  * ``ipv6-cidr-block-association.association-id`` - An association ID for an IPv6 CIDR block associated with the subnet. 
   
  * ``ipv6-cidr-block-association.state`` - The state of an IPv6 CIDR block associated with the subnet. 
   
  * ``state`` - The state of the subnet (``pending`` | ``available`` ). 
   
  * ``subnet-id`` - The ID of the subnet. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``vpc-id`` - The ID of the VPC for the subnet. 
   

  



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



``--subnet-ids`` (list)


  One or more subnet IDs.

   

  Default: Describes all your subnets.

  



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

**To describe your subnets**

This example describes your subnets.

Command::

  aws ec2 describe-subnets 

Output::

  {
      "Subnets": [
          {
              "VpcId": "vpc-a01106c2",
              "AvailableIpAddressCount": 251,
              "MapPublicIpOnLaunch": false,
              "DefaultForAz": false,
              "Ipv6CidrBlockAssociationSet": [],
              "State": "available",
              "AvailabilityZone": "us-east-1c",
              "SubnetId": "subnet-9d4a7b6c",
              "CidrBlock": "10.0.1.0/24",
              "AssignIpv6AddressOnCreation": false
          },
          {
            "VpcId": "vpc-31896b55", 
            "AvailableIpAddressCount": 251, 
            "MapPublicIpOnLaunch": false, 
            "DefaultForAz": false, 
            "Ipv6CidrBlockAssociationSet": [
                {
                    "Ipv6CidrBlock": "2001:db8:1234:a101::/64", 
                    "AssociationId": "subnet-cidr-assoc-30e7e348", 
                    "Ipv6CidrBlockState": {
                        "State": "ASSOCIATED"
                    }
                }
            ], 
            "State": "available", 
            "AvailabilityZone": "us-east-1a", 
            "SubnetId": "subnet-4204d234", 
            "CidrBlock": "10.0.1.0/24", 
            "AssignIpv6AddressOnCreation": false
        }
      ]  
  }
  
**To describe the subnets for a specific VPC**

This example describes the subnets for the specified VPC.

Command::

  aws ec2 describe-subnets --filters "Name=vpc-id,Values=vpc-a01106c2"

**To describe subnets with a specific tag**

This example lists subnets with the tag ``Name=MySubnet`` and returns the output in text format.

Command::

  aws ec2 describe-subnets --filters Name=tag:Name,Values=MySubnet --output text

Output::

  SUBNETS	False	us-east-1a	251	10.0.1.0/24	False	False	available	subnet-5f46ec3b	vpc-a034d6c4
  TAGS	Name	MySubnet

======
Output
======

Subnets -> (list)

  

  Information about one or more subnets.

  

  (structure)

    

    Describes a subnet.

    

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

          

          

        

      

    

  

