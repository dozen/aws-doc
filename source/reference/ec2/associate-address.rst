[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 associate-address:


*****************
associate-address
*****************



===========
Description
===========



Associates an Elastic IP address with an instance or a network interface.

 

An Elastic IP address is for use in either the EC2-Classic platform or in a VPC. For more information, see `Elastic IP Addresses`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

[EC2-Classic, VPC in an EC2-VPC-only account] If the Elastic IP address is already associated with a different instance, it is disassociated from that instance and associated with the specified instance.

 

[VPC in an EC2-Classic account] If you don't specify a private IP address, the Elastic IP address is associated with the primary IP address. If the Elastic IP address is already associated with a different instance or a network interface, you get an error unless you allow reassociation.

 

This is an idempotent operation. If you perform the operation more than once, Amazon EC2 doesn't return an error.



========
Synopsis
========

::

    associate-address
  [--dry-run | --no-dry-run]
  [--instance-id <value>]
  [--public-ip <value>]
  [--allocation-id <value>]
  [--network-interface-id <value>]
  [--private-ip-address <value>]
  [--allow-reassociation | --no-allow-reassociation]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-id`` (string)


  The ID of the instance. This is required for EC2-Classic. For EC2-VPC, you can specify either the instance ID or the network interface ID, but not both. The operation fails if you specify an instance ID unless exactly one network interface is attached. 

  

``--public-ip`` (string)


  The Elastic IP address. This is required for EC2-Classic.

  

``--allocation-id`` (string)


  [EC2-VPC] The allocation ID. This is required for EC2-VPC.

  

``--network-interface-id`` (string)


  [EC2-VPC] The ID of the network interface. If the instance has more than one network interface, you must specify a network interface ID.

  

``--private-ip-address`` (string)


  [EC2-VPC] The primary or secondary private IP address to associate with the Elastic IP address. If no private IP address is specified, the Elastic IP address is associated with the primary private IP address.

  

``--allow-reassociation`` | ``--no-allow-reassociation`` (boolean)


  [EC2-VPC] For a VPC in an EC2-Classic account, specify true to allow an Elastic IP address that is already associated with an instance or network interface to be reassociated with the specified instance or network interface. Otherwise, the operation fails. In a VPC in an EC2-VPC-only account, reassociation is automatic, therefore you can specify false to ensure the operation fails if the Elastic IP address is already associated with another resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To associate an Elastic IP addresses in EC2-Classic**

This example associates an Elastic IP address with an instance in EC2-Classic. If the command succeeds, no output is returned.

Command::

  aws ec2 associate-address --instance-id i-5203422c --public-ip 198.51.100.0

**To associate an Elastic IP address in EC2-VPC**

This example associates an Elastic IP address with an instance in a VPC.

Command::

  aws ec2 associate-address --instance-id i-43a4412a --allocation-id eipalloc-64d5890a

Output::

  {
      "AssociationId": "eipassoc-2bebb745"
  }

This example associates an Elastic IP address with a network interface.

Command::

  aws ec2 associate-address --allocation-id eipalloc-64d5890a --network-interface-id eni-1a2b3c4d

This example associates an Elastic IP with a private IP address that's associated with a network interface.

Command::

  aws ec2 associate-address --allocation-id eipalloc-64d5890a --network-interface-id eni-1a2b3c4d --private-ip-address 10.0.0.85

 


======
Output
======

AssociationId -> (string)

  

  [EC2-VPC] The ID that represents the association of the Elastic IP address with an instance.

  

  



.. _Elastic IP Addresses: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html
