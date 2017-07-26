[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-vpn-connection-route:


***************************
create-vpn-connection-route
***************************



===========
Description
===========



Creates a static route associated with a VPN connection between an existing virtual private gateway and a VPN customer gateway. The static route allows traffic to be routed from the virtual private gateway to the VPN customer gateway.

 

For more information about VPN connections, see `Adding a Hardware Virtual Private Gateway to Your VPC`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    create-vpn-connection-route
  --vpn-connection-id <value>
  --destination-cidr-block <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--vpn-connection-id`` (string)


  The ID of the VPN connection.

  

``--destination-cidr-block`` (string)


  The CIDR block associated with the local subnet of the customer network.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

.. _Adding a Hardware Virtual Private Gateway to Your VPC: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_VPN.html
