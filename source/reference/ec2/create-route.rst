[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-route:


************
create-route
************



===========
Description
===========



Creates a route in a route table within a VPC.

 

You must specify one of the following targets: Internet gateway or virtual private gateway, NAT instance, NAT gateway, VPC peering connection, network interface, or egress-only Internet gateway.

 

When determining how to route traffic, we use the route with the most specific match. For example, traffic is destined for the IPv4 address ``192.0.2.3`` , and the route table includes the following two IPv4 routes:

 

 
* ``192.0.2.0/24`` (goes to some target A) 
 
* ``192.0.2.0/28`` (goes to some target B) 
 

 

Both routes apply to the traffic destined for ``192.0.2.3`` . However, the second route in the list covers a smaller number of IP addresses and is therefore more specific, so we use that route to determine where to target the traffic.

 

For more information about route tables, see `Route Tables <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Route_Tables.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateRoute>`_


========
Synopsis
========

::

    create-route
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


  The IPv4 CIDR address block used for the destination match. Routing decisions are based on the most specific match.

  

``--destination-ipv6-cidr-block`` (string)


  The IPv6 CIDR block used for the destination match. Routing decisions are based on the most specific match.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--egress-only-internet-gateway-id`` (string)


  [IPv6 traffic only] The ID of an egress-only Internet gateway.

  

``--gateway-id`` (string)


  The ID of an Internet gateway or virtual private gateway attached to your VPC.

  

``--instance-id`` (string)


  The ID of a NAT instance in your VPC. The operation fails if you specify an instance ID unless exactly one network interface is attached.

  

``--nat-gateway-id`` (string)


  [IPv4 traffic only] The ID of a NAT gateway.

  

``--network-interface-id`` (string)


  The ID of a network interface.

  

``--route-table-id`` (string)


  The ID of the route table for the route.

  

``--vpc-peering-connection-id`` (string)


  The ID of a VPC peering connection.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a route**

This example creates a route for the specified route table. The route matches all IPv4 traffic (``0.0.0.0/0``) and routes it to the specified Internet gateway. If the command succeeds, no output is returned.

Command::

  aws ec2 create-route --route-table-id rtb-22574640 --destination-cidr-block 0.0.0.0/0 --gateway-id igw-c0a643a9

This example command creates a route in route table rtb-g8ff4ea2. The route matches traffic for the IPv4 CIDR block
10.0.0.0/16 and routes it to VPC peering connection, pcx-111aaa22. This route enables traffic to be directed to the peer
VPC in the VPC peering connection. If the command succeeds, no output is returned.

Command::

  aws ec2 create-route --route-table-id rtb-g8ff4ea2 --destination-cidr-block 10.0.0.0/16 --vpc-peering-connection-id pcx-1a2b3c4d
  
This example creates a route in the specified route table that matches all IPv6 traffic (``::/0``) and routes it to the specified egress-only Internet gateway. 

Command::

  aws ec2 create-route --route-table-id rtb-dce620b8 --destination-ipv6-cidr-block ::/0 --egress-only-internet-gateway-id eigw-01eadbd45ecd7943f


======
Output
======

Return -> (boolean)

  

  Returns ``true`` if the request succeeds; otherwise, it returns an error.

  

  

