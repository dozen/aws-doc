[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 assign-private-ip-addresses:


***************************
assign-private-ip-addresses
***************************



===========
Description
===========



Assigns one or more secondary private IP addresses to the specified network interface. You can specify one or more specific secondary IP addresses, or you can specify the number of secondary IP addresses to be automatically assigned within the subnet's CIDR block range. The number of secondary IP addresses that you can assign to an instance varies by instance type. For information about instance types, see `Instance Types`_ in the *Amazon Elastic Compute Cloud User Guide* . For more information about Elastic IP addresses, see `Elastic IP Addresses`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

assign-private-ip-addresses is available only in EC2-VPC.



========
Synopsis
========

::

    assign-private-ip-addresses
  --network-interface-id <value>
  [--private-ip-addresses <value>]
  [--secondary-private-ip-address-count <value>]
  [--allow-reassignment | --no-allow-reassignment]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--network-interface-id`` (string)


  The ID of the network interface.

  

``--private-ip-addresses`` (list)


  One or more IP addresses to be assigned as a secondary private IP address to the network interface. You can't specify this parameter when also specifying a number of secondary IP addresses.

   

  If you don't specify an IP address, Amazon EC2 automatically selects an IP address within the subnet range.

  



Syntax::

  "string" "string" ...



``--secondary-private-ip-address-count`` (integer)


  The number of secondary IP addresses to assign to the network interface. You can't specify this parameter when also specifying private IP addresses.

  

``--allow-reassignment`` | ``--no-allow-reassignment`` (boolean)


  Indicates whether to allow an IP address that is already assigned to another network interface or instance to be reassigned to the specified network interface.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To assign a specific secondary private IP address a network interface**

This example assigns the specified secondary private IP address to the specified network interface. If the command succeeds, no output is returned. 

Command::

  aws ec2 assign-private-ip-addresses --network-interface-id eni-e5aa89a3 --private-ip-addresses 10.0.0.82

**To assign secondary private IP addresses that Amazon EC2 selects to a network interface**

This example assigns two secondary private IP addresses to the specified network interface. Amazon EC2 automatically assigns these IP addresses from the available IP addresses in the CIDR block range of the subnet the network interface is associated with. If the command succeeds, no output is returned.

Command::

  aws ec2 assign-private-ip-addresses --network-interface-id eni-e5aa89a3 --secondary-private-ip-address-count 2


======
Output
======

None

.. _Elastic IP Addresses: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html
.. _Instance Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html
