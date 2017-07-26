[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 attach-network-interface:


************************
attach-network-interface
************************



===========
Description
===========



Attaches a network interface to an instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AttachNetworkInterface>`_


========
Synopsis
========

::

    attach-network-interface
  --device-index <value>
  [--dry-run | --no-dry-run]
  --instance-id <value>
  --network-interface-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--device-index`` (integer)


  The index of the device for the network interface attachment.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-id`` (string)


  The ID of the instance.

  

``--network-interface-id`` (string)


  The ID of the network interface.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To attach a network interface to an instance**

This example attaches the specified network interface to the specified instance.

Command::

  aws ec2 attach-network-interface --network-interface-id eni-e5aa89a3 --instance-id i-1234567890abcdef0 --device-index 1

Output::

  {
      "AttachmentId": "eni-attach-66c4350a"
  }

======
Output
======

AttachmentId -> (string)

  

  The ID of the network interface attachment.

  

  

