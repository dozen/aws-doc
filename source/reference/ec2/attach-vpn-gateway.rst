[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 attach-vpn-gateway:


******************
attach-vpn-gateway
******************



===========
Description
===========



Attaches a virtual private gateway to a VPC. For more information, see `Adding a Hardware Virtual Private Gateway to Your VPC`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    attach-vpn-gateway
  [--dry-run | --no-dry-run]
  --vpn-gateway-id <value>
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpn-gateway-id`` (string)


  The ID of the virtual private gateway.

  

``--vpc-id`` (string)


  The ID of the VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  VpcId -> (string)

    

    The ID of the VPC.

    

    

  State -> (string)

    

    The current state of the attachment.

    

    

  



.. _Adding a Hardware Virtual Private Gateway to Your VPC: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_VPN.html
