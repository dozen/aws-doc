[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 reset-network-interface-attribute:


*********************************
reset-network-interface-attribute
*********************************



===========
Description
===========



Resets a network interface attribute. You can specify only one attribute at a time.



========
Synopsis
========

::

    reset-network-interface-attribute
  [--dry-run | --no-dry-run]
  --network-interface-id <value>
  [--source-dest-check <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--network-interface-id`` (string)


  The ID of the network interface.

  

``--source-dest-check`` (string)


  The source/destination checking attribute. Resets the value to ``true`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None