[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 detach-internet-gateway:


***********************
detach-internet-gateway
***********************



===========
Description
===========



Detaches an Internet gateway from a VPC, disabling connectivity between the Internet and the VPC. The VPC must not contain any running instances with Elastic IP addresses.



========
Synopsis
========

::

    detach-internet-gateway
  [--dry-run | --no-dry-run]
  --internet-gateway-id <value>
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--internet-gateway-id`` (string)


  The ID of the Internet gateway.

  

``--vpc-id`` (string)


  The ID of the VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To detach an Internet gateway from your VPC**

This example detaches the specified Internet gateway from the specified VPC. If the command succeeds, no output is returned.

Command::

  aws ec2 detach-internet-gateway --internet-gateway-id igw-c0a643a9 --vpc-id vpc-a01106c2


======
Output
======

None