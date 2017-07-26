[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 disable-vgw-route-propagation:


*****************************
disable-vgw-route-propagation
*****************************



===========
Description
===========



Disables a virtual private gateway (VGW) from propagating routes to a specified route table of a VPC.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DisableVgwRoutePropagation>`_


========
Synopsis
========

::

    disable-vgw-route-propagation
  --gateway-id <value>
  --route-table-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--gateway-id`` (string)


  The ID of the virtual private gateway.

  

``--route-table-id`` (string)


  The ID of the route table.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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