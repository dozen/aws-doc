[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-vpn-gateways:


*********************
describe-vpn-gateways
*********************



===========
Description
===========



Describes one or more of your virtual private gateways.

 

For more information about virtual private gateways, see `Adding an IPsec Hardware VPN to Your VPC`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    describe-vpn-gateways
  [--dry-run | --no-dry-run]
  [--vpn-gateway-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpn-gateway-ids`` (list)


  One or more virtual private gateway IDs.

   

  Default: Describes all your virtual private gateways.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``attachment.state`` - The current state of the attachment between the gateway and the VPC (``attaching`` | ``attached`` | ``detaching`` | ``detached`` ). 
   
  * ``attachment.vpc-id`` - The ID of an attached VPC. 
   
  * ``availability-zone`` - The Availability Zone for the virtual private gateway (if applicable). 
   
  * ``state`` - The state of the virtual private gateway (``pending`` | ``available`` | ``deleting`` | ``deleted`` ). 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``type`` - The type of virtual private gateway. Currently the only supported type is ``ipsec.1`` . 
   
  * ``vpn-gateway-id`` - The ID of the virtual private gateway. 
   

  



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

**To describe your virtual private gateways**

This example describes your virtual private gateways.

Command::

  aws ec2 describe-vpn-gateways

Output::

  {
      "VpnGateways": [
          {
              "State": "available",
              "Type": "ipsec.1",
              "VpnGatewayId": "vgw-f211f09b",
              "VpcAttachments": [
                  {
                      "State": "attached",
                      "VpcId": "vpc-98eb5ef5"
                  }
              ]
          },
          {
              "State": "available",
              "Type": "ipsec.1",
              "VpnGatewayId": "vgw-9a4cacf3",
              "VpcAttachments": [
                  {
                      "State": "attaching",
                      "VpcId": "vpc-a01106c2"
                  }
              ]
          }
      ]  
  }

======
Output
======

VpnGateways -> (list)

  

  Information about one or more virtual private gateways.

  

  (structure)

    

    Describes a virtual private gateway.

    

    VpnGatewayId -> (string)

      

      The ID of the virtual private gateway.

      

      

    State -> (string)

      

      The current state of the virtual private gateway.

      

      

    Type -> (string)

      

      The type of VPN connection the virtual private gateway supports.

      

      

    AvailabilityZone -> (string)

      

      The Availability Zone where the virtual private gateway was created, if applicable. This field may be empty or not returned. 

      

      

    VpcAttachments -> (list)

      

      Any VPCs attached to the virtual private gateway.

      

      (structure)

        

        Describes an attachment between a virtual private gateway and a VPC.

        

        VpcId -> (string)

          

          The ID of the VPC.

          

          

        State -> (string)

          

          The current state of the attachment.

          

          

        

      

    Tags -> (list)

      

      Any tags assigned to the virtual private gateway.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag. 

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    

  



.. _Adding an IPsec Hardware VPN to Your VPC: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_VPN.html
