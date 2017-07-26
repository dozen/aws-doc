[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-egress-only-internet-gateway:


***********************************
create-egress-only-internet-gateway
***********************************



===========
Description
===========



[IPv6 only] Creates an egress-only Internet gateway for your VPC. An egress-only Internet gateway is used to enable outbound communication over IPv6 from instances in your VPC to the Internet, and prevents hosts outside of your VPC from initiating an IPv6 connection with your instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateEgressOnlyInternetGateway>`_


========
Synopsis
========

::

    create-egress-only-internet-gateway
  [--client-token <value>]
  [--dry-run | --no-dry-run]
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure the idempotency of the request. For more information, see `How to Ensure Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Run_Instance_Idempotency.html>`_ .

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-id`` (string)


  The ID of the VPC for which to create the egress-only Internet gateway.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an egress-only Internet gateway**

This example creates an egress-only Internet gateway for the specified VPC.

Command::

  aws ec2 create-egress-only-internet-gateway --vpc-id vpc-0c62a468

Output::

  {
    "EgressOnlyInternetGateway": {
        "EgressOnlyInternetGatewayId": "eigw-015e0e244e24dfe8a", 
        "Attachments": [
            {
                "State": "attached", 
                "VpcId": "vpc-0c62a468"
            }
        ]
    }
  }

======
Output
======

ClientToken -> (string)

  

  Unique, case-sensitive identifier you provide to ensure the idempotency of the request.

  

  

EgressOnlyInternetGateway -> (structure)

  

  Information about the egress-only Internet gateway.

  

  Attachments -> (list)

    

    Information about the attachment of the egress-only Internet gateway.

    

    (structure)

      

      Describes the attachment of a VPC to an Internet gateway or an egress-only Internet gateway.

      

      State -> (string)

        

        The current state of the attachment.

        

        

      VpcId -> (string)

        

        The ID of the VPC.

        

        

      

    

  EgressOnlyInternetGatewayId -> (string)

    

    The ID of the egress-only Internet gateway.

    

    

  

