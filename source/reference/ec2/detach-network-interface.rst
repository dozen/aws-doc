[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 detach-network-interface:


************************
detach-network-interface
************************



===========
Description
===========



Detaches a network interface from an instance.



========
Synopsis
========

::

    detach-network-interface
  [--dry-run | --no-dry-run]
  --attachment-id <value>
  [--force | --no-force]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--attachment-id`` (string)


  The ID of the attachment.

  

``--force`` | ``--no-force`` (boolean)


  Specifies whether to force a detachment.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To detach a network interface from your instance**

This example detaches the specified network interface from the specified instance. If the command succeeds, no output is returned.

Command::

  aws ec2 detach-network-interface --attachment-id eni-attach-66c4350a


======
Output
======

None