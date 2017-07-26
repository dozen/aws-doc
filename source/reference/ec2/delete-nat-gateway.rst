[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-nat-gateway:


******************
delete-nat-gateway
******************



===========
Description
===========



Deletes the specified NAT gateway. Deleting a NAT gateway disassociates its Elastic IP address, but does not release the address from your account. Deleting a NAT gateway does not delete any NAT gateway routes in your route tables.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DeleteNatGateway>`_


========
Synopsis
========

::

    delete-nat-gateway
  --nat-gateway-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--nat-gateway-id`` (string)


  The ID of the NAT gateway.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a NAT gateway**

This example deletes NAT gateway ``nat-04ae55e711cec5680``.

Command::

  aws ec2 delete-nat-gateway --nat-gateway-id nat-04ae55e711cec5680

Output::
 
 {
    "NatGatewayId": "nat-04ae55e711cec5680"
 }


======
Output
======

NatGatewayId -> (string)

  

  The ID of the NAT gateway.

  

  

