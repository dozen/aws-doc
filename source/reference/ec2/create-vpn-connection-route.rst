[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-vpn-connection-route:


***************************
create-vpn-connection-route
***************************



===========
Description
===========



Creates a static route associated with a VPN connection between an existing virtual private gateway and a VPN customer gateway. The static route allows traffic to be routed from the virtual private gateway to the VPN customer gateway.

 

For more information about VPN connections, see `Adding a Hardware Virtual Private Gateway to Your VPC <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_VPN.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateVpnConnectionRoute>`_


========
Synopsis
========

::

    create-vpn-connection-route
  --destination-cidr-block <value>
  --vpn-connection-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--destination-cidr-block`` (string)


  The CIDR block associated with the local subnet of the customer network.

  

``--vpn-connection-id`` (string)


  The ID of the VPN connection.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a static route for a VPN connection**

This example creates a static route for the specified VPN connection. If the command succeeds, no output is returned.

Command::

  aws ec2 create-vpn-connection-route --vpn-connection-id vpn-40f41529 --destination-cidr-block 11.12.0.0/16


======
Output
======

None