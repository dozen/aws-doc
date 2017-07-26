[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 unassign-ipv6-addresses:


***********************
unassign-ipv6-addresses
***********************



===========
Description
===========



Unassigns one or more IPv6 addresses from a network interface.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/UnassignIpv6Addresses>`_


========
Synopsis
========

::

    unassign-ipv6-addresses
  --ipv6-addresses <value>
  --network-interface-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ipv6-addresses`` (list)


  The IPv6 addresses to unassign from the network interface.

  



Syntax::

  "string" "string" ...



``--network-interface-id`` (string)


  The ID of the network interface.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To unassign an IPv6 address from a network interface**

This example unassigns the specified IPv6 address from the specified network interface.

Command::

  aws ec2 unassign-ipv6-addresses --ipv6-addresses 2001:db8:1234:1a00:3304:8879:34cf:4071 --network-interface-id eni-23c49b68

Output::

  {
    "NetworkInterfaceId": "eni-23c49b68", 
    "UnassignedIpv6Addresses": [
        "2001:db8:1234:1a00:3304:8879:34cf:4071"
    ]
  }


======
Output
======

NetworkInterfaceId -> (string)

  

  The ID of the network interface.

  

  

UnassignedIpv6Addresses -> (list)

  

  The IPv6 addresses that have been unassigned from the network interface.

  

  (string)

    

    

  

