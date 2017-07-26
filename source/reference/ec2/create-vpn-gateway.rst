[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-vpn-gateway:


******************
create-vpn-gateway
******************



===========
Description
===========



Creates a virtual private gateway. A virtual private gateway is the endpoint on the VPC side of your VPN connection. You can create a virtual private gateway before creating the VPC itself.

 

For more information about virtual private gateways, see `Adding a Hardware Virtual Private Gateway to Your VPC <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_VPN.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateVpnGateway>`_


========
Synopsis
========

::

    create-vpn-gateway
  [--availability-zone <value>]
  --type <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--availability-zone`` (string)


  The Availability Zone for the virtual private gateway.

  

``--type`` (string)


  The type of VPN connection this virtual private gateway supports.

  

  Possible values:

  
  *   ``ipsec.1``

  

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  AvailabilityZone -> (string)

    

    The Availability Zone where the virtual private gateway was created, if applicable. This field may be empty or not returned.

    

    

  State -> (string)

    

    The current state of the virtual private gateway.

    

    

  Type -> (string)

    

    The type of VPN connection the virtual private gateway supports.

    

    

  VpcAttachments -> (list)

    

    Any VPCs attached to the virtual private gateway.

    

    (structure)

      

      Describes an attachment between a virtual private gateway and a VPC.

      

      State -> (string)

        

        The current state of the attachment.

        

        

      VpcId -> (string)

        

        The ID of the VPC.

        

        

      

    

  VpnGatewayId -> (string)

    

    The ID of the virtual private gateway.

    

    

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

        

        

      

    

  

