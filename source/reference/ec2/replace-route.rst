[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 replace-route:


*************
replace-route
*************



===========
Description
===========



Replaces an existing route within a route table in a VPC. You must provide only one of the following: Internet gateway or virtual private gateway, NAT instance, NAT gateway, VPC peering connection, network interface, or egress-only Internet gateway.

 

For more information about route tables, see `Route Tables <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Route_Tables.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ReplaceRoute>`_


========
Synopsis
========

::

    replace-route
  [--destination-cidr-block <value>]
  [--destination-ipv6-cidr-block <value>]
  [--dry-run | --no-dry-run]
  [--egress-only-internet-gateway-id <value>]
  [--gateway-id <value>]
  [--instance-id <value>]
  [--nat-gateway-id <value>]
  [--network-interface-id <value>]
  --route-table-id <value>
  [--vpc-peering-connection-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--destination-cidr-block`` (string)


  The IPv4 CIDR address block used for the destination match. The value you provide must match the CIDR of an existing route in the table.

  

``--destination-ipv6-cidr-block`` (string)


  The IPv6 CIDR address block used for the destination match. The value you provide must match the CIDR of an existing route in the table.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--egress-only-internet-gateway-id`` (string)


  [IPv6 traffic only] The ID of an egress-only Internet gateway.

  

``--gateway-id`` (string)


  The ID of an Internet gateway or virtual private gateway.

  

``--instance-id`` (string)


  The ID of a NAT instance in your VPC.

  

``--nat-gateway-id`` (string)


  [IPv4 traffic only] The ID of a NAT gateway.

  

``--network-interface-id`` (string)


  The ID of a network interface.

  

``--route-table-id`` (string)


  The ID of the route table.

  

``--vpc-peering-connection-id`` (string)


  The ID of a VPC peering connection.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To replace a route**

This example replaces the specified route in the specified table table. The new route matches the specified CIDR and sends the traffic to the specified virtual private gateway. If the command succeeds, no output is returned.

Command::

  aws ec2 replace-route --route-table-id rtb-22574640 --destination-cidr-block 10.0.0.0/16 --gateway-id vgw-9a4cacf3

======
Output
======

None