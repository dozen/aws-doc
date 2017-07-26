[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 attach-network-interface:


************************
attach-network-interface
************************



===========
Description
===========



Attaches a network interface to an instance.



========
Synopsis
========

::

    attach-network-interface
  [--dry-run | --no-dry-run]
  --network-interface-id <value>
  --instance-id <value>
  --device-index <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--network-interface-id`` (string)


  The ID of the network interface.

  

``--instance-id`` (string)


  The ID of the instance.

  

``--device-index`` (integer)


  The index of the device for the network interface attachment.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To attach a network interface to an instance**

This example attaches the specified network interface to the specified instance.

Command::

  aws ec2 attach-network-interface --network-interface-id eni-e5aa89a3 --instance-id i-640a3c17 --device-index 1

Output::

  {
      "AttachmentId": "eni-attach-66c4350a"
  }

======
Output
======

AttachmentId -> (string)

  

  The ID of the network interface attachment.

  

  

