[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 disable-vgw-route-propagation:


*****************************
disable-vgw-route-propagation
*****************************



===========
Description
===========



Disables a virtual private gateway (VGW) from propagating routes to a specified route table of a VPC.



========
Synopsis
========

::

    disable-vgw-route-propagation
  --route-table-id <value>
  --gateway-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--route-table-id`` (string)


  The ID of the route table.

  

``--gateway-id`` (string)


  The ID of the virtual private gateway.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To disable route propagation**

This example disables the specified virtual private gateway from propagating static routes to the specified route table. If the command succeeds, no output is returned.

Command::

  aws ec2 disable-vgw-route-propagation --route-table-id rtb-22574640 --gateway-id vgw-9a4cacf3


======
Output
======

None