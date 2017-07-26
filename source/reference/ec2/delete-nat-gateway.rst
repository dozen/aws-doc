[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-nat-gateway:


******************
delete-nat-gateway
******************



===========
Description
===========



Deletes the specified NAT gateway. Deleting a NAT gateway disassociates its Elastic IP address, but does not release the address from your account. Deleting a NAT gateway does not delete any NAT gateway routes in your route tables. 



========
Synopsis
========

::

    delete-nat-gateway
  --nat-gateway-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--nat-gateway-id`` (string)


  The ID of the NAT gateway.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  

