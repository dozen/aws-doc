[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 replace-route:


*************
replace-route
*************



===========
Description
===========



Replaces an existing route within a route table in a VPC. You must provide only one of the following: Internet gateway or virtual private gateway, NAT instance, NAT gateway, VPC peering connection, or network interface.

 

For more information about route tables, see `Route Tables`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    replace-route
  [--dry-run | --no-dry-run]
  --route-table-id <value>
  --destination-cidr-block <value>
  [--gateway-id <value>]
  [--instance-id <value>]
  [--network-interface-id <value>]
  [--vpc-peering-connection-id <value>]
  [--nat-gateway-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--route-table-id`` (string)


  The ID of the route table.

  

``--destination-cidr-block`` (string)


  The CIDR address block used for the destination match. The value you provide must match the CIDR of an existing route in the table.

  

``--gateway-id`` (string)


  The ID of an Internet gateway or virtual private gateway.

  

``--instance-id`` (string)


  The ID of a NAT instance in your VPC.

  

``--network-interface-id`` (string)


  The ID of a network interface.

  

``--vpc-peering-connection-id`` (string)


  The ID of a VPC peering connection.

  

``--nat-gateway-id`` (string)


  The ID of a NAT gateway.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

.. _Route Tables: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Route_Tables.html
