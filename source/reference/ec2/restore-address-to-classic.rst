[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 restore-address-to-classic:


**************************
restore-address-to-classic
**************************



===========
Description
===========



Restores an Elastic IP address that was previously moved to the EC2-VPC platform back to the EC2-Classic platform. You cannot move an Elastic IP address that was originally allocated for use in EC2-VPC. The Elastic IP address must not be associated with an instance or network interface. You cannot restore an Elastic IP address that's associated with a reverse DNS record. Contact AWS account and billing support to remove the reverse DNS record. 



========
Synopsis
========

::

    restore-address-to-classic
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

**To restore an address to EC2-Classic**

This example restores Elastic IP address 198.51.100.0 to the EC2-Classic platform.

Command::

  aws ec2 restore-address-to-classic --public-ip 198.51.100.0

Output::

  {
    "Status": "MoveInProgress", 
    "PublicIp": "198.51.100.0"
  }


======
Output
======

Status -> (string)

  

  The move status for the IP address.

  

  

PublicIp -> (string)

  

  The Elastic IP address.

  

  

