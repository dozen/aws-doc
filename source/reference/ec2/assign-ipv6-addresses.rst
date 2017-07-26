[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 assign-ipv6-addresses:


*********************
assign-ipv6-addresses
*********************



===========
Description
===========



Assigns one or more IPv6 addresses to the specified network interface. You can specify one or more specific IPv6 addresses, or you can specify the number of IPv6 addresses to be automatically assigned from within the subnet's IPv6 CIDR block range. You can assign as many IPv6 addresses to a network interface as you can assign private IPv4 addresses, and the limit varies per instance type. For information, see `IP Addresses Per Network Interface Per Instance Type <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html#AvailableIpPerENI>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AssignIpv6Addresses>`_


========
Synopsis
========

::

    assign-ipv6-addresses
  [--ipv6-address-count <value>]
  [--ipv6-addresses <value>]
  --network-interface-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ipv6-address-count`` (integer)


  The number of IPv6 addresses to assign to the network interface. Amazon EC2 automatically selects the IPv6 addresses from the subnet range. You can't use this option if specifying specific IPv6 addresses.

  

``--ipv6-addresses`` (list)


  One or more specific IPv6 addresses to be assigned to the network interface. You can't use this option if you're specifying a number of IPv6 addresses.

  



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

**To assign specific IPv6 addresses to a network interface**

This example assigns the specified IPv6 addresses to the specified network interface.

Command::

  aws ec2 assign-ipv6-addresses --network-interface-id eni-38664473 --ipv6-addresses 2001:db8:1234:1a00:3304:8879:34cf:4071 2001:db8:1234:1a00:9691:9503:25ad:1761

Output::

  {
    "AssignedIpv6Addresses": [
        "2001:db8:1234:1a00:3304:8879:34cf:4071", 
        "2001:db8:1234:1a00:9691:9503:25ad:1761"
    ], 
    "NetworkInterfaceId": "eni-38664473"
  }

**To assign IPv6 addresses that Amazon selects to a network interface**

This example assigns two IPv6 addresses to the specified network interface. Amazon automatically assigns these IPv6 addresses from the available IPv6 addresses in the IPv6 CIDR block range of the subnet.

Command::

  aws ec2 assign-ipv6-addresses --network-interface-id eni-38664473 --ipv6-address-count 2

Output::

  {
    "AssignedIpv6Addresses": [
        "2001:db8:1234:1a00:3304:8879:34cf:4071", 
        "2001:db8:1234:1a00:9691:9503:25ad:1761"
    ], 
    "NetworkInterfaceId": "eni-38664473"
  }


======
Output
======

AssignedIpv6Addresses -> (list)

  

  The IPv6 addresses assigned to the network interface.

  

  (string)

    

    

  

NetworkInterfaceId -> (string)

  

  The ID of the network interface.

  

  

