[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 unassign-private-ip-addresses:


*****************************
unassign-private-ip-addresses
*****************************



===========
Description
===========



Unassigns one or more secondary private IP addresses from a network interface.



========
Synopsis
========

::

    unassign-private-ip-addresses
  --network-interface-id <value>
  --private-ip-addresses <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--network-interface-id`` (string)


  The ID of the network interface.

  

``--private-ip-addresses`` (list)


  The secondary private IP addresses to unassign from the network interface. You can specify this option multiple times to unassign more than one IP address.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To unassign a secondary private IP address from a network interface**

This example unassigns the specified private IP address from the specified network interface. If the command succeeds, no output is returned.

Command::

  aws ec2 unassign-private-ip-addresses --network-interface-id eni-e5aa89a3 --private-ip-addresses 10.0.0.82


======
Output
======

None