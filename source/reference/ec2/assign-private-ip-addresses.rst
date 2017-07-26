[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 assign-private-ip-addresses:


***************************
assign-private-ip-addresses
***************************



===========
Description
===========



Assigns one or more secondary private IP addresses to the specified network interface. You can specify one or more specific secondary IP addresses, or you can specify the number of secondary IP addresses to be automatically assigned within the subnet's CIDR block range. The number of secondary IP addresses that you can assign to an instance varies by instance type. For information about instance types, see `Instance Types <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html>`_ in the *Amazon Elastic Compute Cloud User Guide* . For more information about Elastic IP addresses, see `Elastic IP Addresses <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

assign-private-ip-addresses is available only in EC2-VPC.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AssignPrivateIpAddresses>`_


========
Synopsis
========

::

    assign-private-ip-addresses
  [--allow-reassignment | --no-allow-reassignment]
  --network-interface-id <value>
  [--private-ip-addresses <value>]
  [--secondary-private-ip-address-count <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--allow-reassignment`` | ``--no-allow-reassignment`` (boolean)


  Indicates whether to allow an IP address that is already assigned to another network interface or instance to be reassigned to the specified network interface.

  

``--network-interface-id`` (string)


  The ID of the network interface.

  

``--private-ip-addresses`` (list)


  One or more IP addresses to be assigned as a secondary private IP address to the network interface. You can't specify this parameter when also specifying a number of secondary IP addresses.

   

  If you don't specify an IP address, Amazon EC2 automatically selects an IP address within the subnet range.

  



Syntax::

  "string" "string" ...



``--secondary-private-ip-address-count`` (integer)


  The number of secondary IP addresses to assign to the network interface. You can't specify this parameter when also specifying private IP addresses.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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