[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-subnet-attribute:


***********************
modify-subnet-attribute
***********************



===========
Description
===========



Modifies a subnet attribute. You can only modify one attribute at a time.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifySubnetAttribute>`_


========
Synopsis
========

::

    modify-subnet-attribute
  [--assign-ipv6-address-on-creation | --no-assign-ipv6-address-on-creation]
  [--map-public-ip-on-launch | --no-map-public-ip-on-launch]
  --subnet-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assign-ipv6-address-on-creation`` | ``--no-assign-ipv6-address-on-creation`` (structure)


  Specify ``true`` to indicate that network interfaces created in the specified subnet should be assigned an IPv6 address. This includes a network interface that's created when launching an instance into the subnet (the instance therefore receives an IPv6 address). 

   

  If you enable the IPv6 addressing feature for your subnet, your network interface or instance only receives an IPv6 address if it's created using version ``2016-11-15`` or later of the Amazon EC2 API.

  

``--map-public-ip-on-launch`` | ``--no-map-public-ip-on-launch`` (structure)


  Specify ``true`` to indicate that network interfaces created in the specified subnet should be assigned a public IPv4 address. This includes a network interface that's created when launching an instance into the subnet (the instance therefore receives a public IPv4 address).

  

``--subnet-id`` (string)


  The ID of the subnet.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change a subnet's public IPv4 addressing behavior**

This example modifies subnet-1a2b3c4d to specify that all instances launched into this subnet are assigned a public IPv4 address. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-subnet-attribute --subnet-id subnet-1a2b3c4d --map-public-ip-on-launch

**To change a subnet's IPv6 addressing behavior**

This example modifies subnet-1a2b3c4d to specify that all instances launched into this subnet are assigned an IPv6 address from the range of the subnet.

Command::

  aws ec2 modify-subnet-attribute --subnet-id subnet-1a2b3c4d --assign-ipv6-address-on-creation

For more information, see `IP Addressing in Your VPC`_ in the *AWS Virtual Private Cloud User Guide*.

.. _`IP Addressing in Your VPC`: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-ip-addressing.html

======
Output
======

None