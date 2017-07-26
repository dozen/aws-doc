[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-subnet-attribute:


***********************
modify-subnet-attribute
***********************



===========
Description
===========



Modifies a subnet attribute.



========
Synopsis
========

::

    modify-subnet-attribute
  --subnet-id <value>
  [--map-public-ip-on-launch | --no-map-public-ip-on-launch]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--subnet-id`` (string)


  The ID of the subnet.

  

``--map-public-ip-on-launch`` | ``--no-map-public-ip-on-launch`` (structure)


  Specify ``true`` to indicate that instances launched into the specified subnet should be assigned public IP address.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To change a subnet's public IP addressing behavior**

This example modifies subnet-1a2b3c4d to specify that all instances launched into this subnet are assigned a public IP address. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-subnet-attribute --subnet-id subnet-1a2b3c4d --map-public-ip-on-launch

For more information, see `IP Addressing in Your VPC`_ in the *AWS Virtual Private Cloud User Guide*.

.. _`IP Addressing in Your VPC`: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-ip-addressing.html

======
Output
======

None