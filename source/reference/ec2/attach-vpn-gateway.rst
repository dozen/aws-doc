[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 attach-vpn-gateway:


******************
attach-vpn-gateway
******************



===========
Description
===========



Attaches a virtual private gateway to a VPC. You can attach one virtual private gateway to one VPC at a time.

 

For more information, see `Adding a Hardware Virtual Private Gateway to Your VPC <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_VPN.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AttachVpnGateway>`_


========
Synopsis
========

::

    attach-vpn-gateway
  --vpc-id <value>
  --vpn-gateway-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--vpc-id`` (string)


  The ID of the VPC.

  

``--vpn-gateway-id`` (string)


  The ID of the virtual private gateway.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To attach a virtual private gateway to your VPC**

This example attaches the specified virtual private gateway to the specified VPC.

Command::

  aws ec2 attach-vpn-gateway --vpn-gateway-id vgw-9a4cacf3 --vpc-id vpc-a01106c2

Output::

  {
      "VpcAttachement": {
          "State": "attaching",
          "VpcId": "vpc-a01106c2"
      }
  }

======
Output
======

VpcAttachment -> (structure)

  

  Information about the attachment.

  

  State -> (string)

    

    The current state of the attachment.

    

    

  VpcId -> (string)

    

    The ID of the VPC.

    

    

  

