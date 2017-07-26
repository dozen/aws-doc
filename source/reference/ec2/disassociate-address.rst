[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 disassociate-address:


********************
disassociate-address
********************



===========
Description
===========



Disassociates an Elastic IP address from the instance or network interface it's associated with.

 

An Elastic IP address is for use in either the EC2-Classic platform or in a VPC. For more information, see `Elastic IP Addresses`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

This is an idempotent operation. If you perform the operation more than once, Amazon EC2 doesn't return an error.



========
Synopsis
========

::

    disassociate-address
  [--dry-run | --no-dry-run]
  [--public-ip <value>]
  [--association-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--public-ip`` (string)


  [EC2-Classic] The Elastic IP address. Required for EC2-Classic.

  

``--association-id`` (string)


  [EC2-VPC] The association ID. Required for EC2-VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To disassociate an Elastic IP addresses in EC2-Classic**

This example disassociates an Elastic IP address from an instance in EC2-Classic. If the command succeeds, no output is returned.

Command::

  aws ec2 disassociate-address --public-ip 198.51.100.0

**To disassociate an Elastic IP address in EC2-VPC**

This example disassociates an Elastic IP address from an instance in a VPC. If the command succeeds, no output is returned.

Command::

  aws ec2 disassociate-address --association-id eipassoc-2bebb745


======
Output
======

None

.. _Elastic IP Addresses: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html
