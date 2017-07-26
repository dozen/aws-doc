[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-subnets:


****************
describe-subnets
****************



===========
Description
===========



Describes one or more of your subnets.

 

For more information about subnets, see `Your VPC and Subnets`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    describe-subnets
  [--dry-run | --no-dry-run]
  [--subnet-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--subnet-ids`` (list)


  One or more subnet IDs.

   

  Default: Describes all your subnets.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``availabilityZone`` - The Availability Zone for the subnet. You can also use ``availability-zone`` as the filter name. 
   
  * ``available-ip-address-count`` - The number of IP addresses in the subnet that are available. 
   
  * ``cidrBlock`` - The CIDR block of the subnet. The CIDR block you specify must exactly match the subnet's CIDR block for information to be returned for the subnet. You can also use ``cidr`` or ``cidr-block`` as the filter names. 
   
  * ``defaultForAz`` - Indicates whether this is the default subnet for the Availability Zone. You can also use ``default-for-az`` as the filter name. 
   
  * ``state`` - The state of the subnet (``pending`` | ``available`` ). 
   
  * ``subnet-id`` - The ID of the subnet. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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
              "CidrBlock": "10.0.1.0/24",
              "MapPublicIpOnLaunch": false,
              "DefaultForAz": false,
              "State": "available",
              "AvailabilityZone": "us-east-1c",
              "SubnetId": "subnet-9d4a7b6c",
              "AvailableIpAddressCount": 251
          },
          {
              "VpcId": "vpc-b61106d4",
              "CidrBlock": "10.0.0.0/24",
              "MapPublicIpOnLaunch": false,
              "DefaultForAz": false,
              "State": "available",
              "AvailabilityZone": "us-east-1d",
              "SubnetId": "subnet-65ea5f08",
              "AvailableIpAddressCount": 251
          }
      ]  
  }
  
**To describe the subnets for a specific VPC**

This example describes the subnets for the specified VPC.

Command::

  aws ec2 describe-subnets --filters "Name=vpc-id,Values=vpc-a01106c2"

Output::

  {
      "Subnets": [
          {
              "VpcId": "vpc-a01106c2",
              "CidrBlock": "10.0.1.0/24",
              "MapPublicIpOnLaunch": false,
              "DefaultForAz": false,
              "State": "available",
              "AvailabilityZone": "us-east-1c",
              "SubnetId": "subnet-9d4a7b6c",
              "AvailableIpAddressCount": 251
          }
      ]  
  }
  
**To describe subnets with a specific tag**

This example lists subnets with the tag ``Name=MySubnet`` and returns the output in text format.

Command::

  aws ec2 describe-subnets --filters Name=tag:Name,Values=MySubnet --output text

Output::

  SUBNETS	us-east-1a	251	10.0.1.0/24	False	False	available	subnet-1a2b3c4d	vpc-11223344
  TAGS	Name	MySubnet

======
Output
======

Subnets -> (list)

  

  Information about one or more subnets.

  

  (structure)

    

    Describes a subnet.

    

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
