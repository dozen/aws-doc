[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 move-address-to-vpc:


*******************
move-address-to-vpc
*******************



===========
Description
===========



Moves an Elastic IP address from the EC2-Classic platform to the EC2-VPC platform. The Elastic IP address must be allocated to your account for more than 24 hours, and it must not be associated with an instance. After the Elastic IP address is moved, it is no longer available for use in the EC2-Classic platform, unless you move it back using the  restore-address-to-classic request. You cannot move an Elastic IP address that's allocated for use in the EC2-VPC platform to the EC2-Classic platform. You cannot migrate an Elastic IP address that's associated with a reverse DNS record. Contact AWS account and billing support to remove the reverse DNS record. 



========
Synopsis
========

::

    move-address-to-vpc
  [--dry-run | --no-dry-run]
  --public-ip <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--public-ip`` (string)


  The Elastic IP address.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To move an address to EC2-VPC**

This example moves Elastic IP address 54.123.4.56 to the EC2-VPC platform.

Command::

  aws ec2 move-address-to-vpc --public-ip 54.123.4.56

Output::

  {
    "Status": "MoveInProgress"
  }

======
Output
======

AllocationId -> (string)

  

  The allocation ID for the Elastic IP address.

  

  

Status -> (string)

  

  The status of the move of the IP address.

  

  

