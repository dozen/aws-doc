[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-vpcs:


*************
describe-vpcs
*************



===========
Description
===========



Describes one or more of your VPCs.



========
Synopsis
========

::

    describe-vpcs
  [--dry-run | --no-dry-run]
  [--vpc-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-ids`` (list)


  One or more VPC IDs.

   

  Default: Describes all your VPCs.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``cidr`` - The CIDR block of the VPC. The CIDR block you specify must exactly match the VPC's CIDR block for information to be returned for the VPC. Must contain the slash followed by one or two digits (for example, ``/28`` ). 
   
  * ``dhcp-options-id`` - The ID of a set of DHCP options. 
   
  * ``isDefault`` - Indicates whether the VPC is the default VPC. 
   
  * ``state`` - The state of the VPC (``pending`` | ``available`` ). 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      

    

  

