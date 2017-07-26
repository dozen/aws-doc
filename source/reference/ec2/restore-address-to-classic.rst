[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 restore-address-to-classic:


**************************
restore-address-to-classic
**************************



===========
Description
===========



Restores an Elastic IP address that was previously moved to the EC2-VPC platform back to the EC2-Classic platform. You cannot move an Elastic IP address that was originally allocated for use in EC2-VPC. The Elastic IP address must not be associated with an instance or network interface.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/RestoreAddressToClassic>`_


========
Synopsis
========

::

    restore-address-to-classic
  [--dry-run | --no-dry-run]
  --public-ip <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--public-ip`` (string)


  The Elastic IP address.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

PublicIp -> (string)

  

  The Elastic IP address.

  

  

Status -> (string)

  

  The move status for the IP address.

  

  

