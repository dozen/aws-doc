[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 release-address:


***************
release-address
***************



===========
Description
===========



Releases the specified Elastic IP address.

 

After releasing an Elastic IP address, it is released to the IP address pool and might be unavailable to you. Be sure to update your DNS records and any servers or devices that communicate with the address. If you attempt to release an Elastic IP address that you already released, you'll get an ``AuthFailure`` error if the address is already allocated to another AWS account.

 

[EC2-Classic, default VPC] Releasing an Elastic IP address automatically disassociates it from any instance that it's associated with. To disassociate an Elastic IP address without releasing it, use  disassociate-address .

 

[Nondefault VPC] You must use  disassociate-address to disassociate the Elastic IP address before you try to release it. Otherwise, Amazon EC2 returns an error (``InvalidIPAddress.InUse`` ).



========
Synopsis
========

::

    release-address
  [--dry-run | --no-dry-run]
  [--public-ip <value>]
  [--allocation-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--public-ip`` (string)


  [EC2-Classic] The Elastic IP address. Required for EC2-Classic.

  

``--allocation-id`` (string)


  [EC2-VPC] The allocation ID. Required for EC2-VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To release an Elastic IP addresses for EC2-Classic**

This example releases an Elastic IP address for use with instances in EC2-Classic. If the command succeeds, no output is returned.

Command::

  aws ec2 release-address --public-ip 198.51.100.0

**To release an Elastic IP address for EC2-VPC**

This example releases an Elastic IP address for use with instances in a VPC. If the command succeeds, no output is returned.

Command::

  aws ec2 release-address --allocation-id eipalloc-64d5890a


======
Output
======

None