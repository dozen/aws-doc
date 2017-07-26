[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-vpn-gateway:


******************
create-vpn-gateway
******************



===========
Description
===========



Creates a virtual private gateway. A virtual private gateway is the endpoint on the VPC side of your VPN connection. You can create a virtual private gateway before creating the VPC itself.

 

For more information about virtual private gateways, see `Adding a Hardware Virtual Private Gateway to Your VPC`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    create-vpn-gateway
  [--dry-run | --no-dry-run]
  --type <value>
  [--availability-zone <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--type`` (string)


  The type of VPN connection this virtual private gateway supports.

  

  Possible values:

  
  *   ``ipsec.1``

  

  

``--availability-zone`` (string)


  The Availability Zone for the virtual private gateway.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a virtual private gateway**

This example creates a virtual private gateway.

Command::

  aws ec2 create-vpn-gateway --type ipsec.1

Output::

  {
      "VpnGateway": {
          "State": "available",
          "Type": "ipsec.1",
          "VpnGatewayId": "vgw-9a4cacf3",
          "VpcAttachments": []
      }
  }

======
Output
======

VpnGateway -> (structure)

  

  Information about the virtual private gateway.

  

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

        

        

      

    

  



.. _Adding a Hardware Virtual Private Gateway to Your VPC: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_VPN.html
