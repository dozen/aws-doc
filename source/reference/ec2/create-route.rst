[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-route:


************
create-route
************



===========
Description
===========



Creates a route in a route table within a VPC.

 

You must specify one of the following targets: Internet gateway or virtual private gateway, NAT instance, NAT gateway, VPC peering connection, or network interface.

 

When determining how to route traffic, we use the route with the most specific match. For example, let's say the traffic is destined for ``192.0.2.3`` , and the route table includes the following two routes:

 

 
* ``192.0.2.0/24`` (goes to some target A) 
 
* ``192.0.2.0/28`` (goes to some target B) 
 

 

Both routes apply to the traffic destined for ``192.0.2.3`` . However, the second route in the list covers a smaller number of IP addresses and is therefore more specific, so we use that route to determine where to target the traffic.

 

For more information about route tables, see `Route Tables`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    create-route
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


  The ID of the route table for the route.

  

``--destination-cidr-block`` (string)


  The CIDR address block used for the destination match. Routing decisions are based on the most specific match.

  

``--gateway-id`` (string)


  The ID of an Internet gateway or virtual private gateway attached to your VPC.

  

``--instance-id`` (string)


  The ID of a NAT instance in your VPC. The operation fails if you specify an instance ID unless exactly one network interface is attached.

  

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

**To create a route**

This example creates a route for the specified route table. The route matches all traffic (``0.0.0.0/0``) and routes it to the specified Internet gateway. If the command succeeds, no output is returned.

Command::

  aws ec2 create-route --route-table-id rtb-22574640 --destination-cidr-block 0.0.0.0/0 --gateway-id igw-c0a643a9

This example command creates a route in route table rtb-g8ff4ea2. The route matches traffic for the CIDR block
10.0.0.0/16 and routes it to VPC peering connection, pcx-111aaa22. This route enables traffic to be directed to the peer
VPC in the VPC peering connection. If the command succeeds, no output is returned.

Command::

  aws ec2 create-route --route-table-id rtb-g8ff4ea2 --destination-cidr-block 10.0.0.0/16 --vpc-peering-connection-id pcx-1a2b3c4d


======
Output
======

Return -> (boolean)

  

  Returns ``true`` if the request succeeds; otherwise, it returns an error.

  

  



.. _Route Tables: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Route_Tables.html
