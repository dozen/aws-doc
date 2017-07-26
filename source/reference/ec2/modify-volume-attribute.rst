[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-volume-attribute:


***********************
modify-volume-attribute
***********************



===========
Description
===========



Modifies a volume attribute.

 

By default, all I/O operations for the volume are suspended when the data on the volume is determined to be potentially inconsistent, to prevent undetectable, latent data corruption. The I/O access to the volume can be resumed by first enabling I/O access and then checking the data consistency on your volume.

 

You can change the default behavior to resume I/O operations. We recommend that you change this only for boot volumes or for volumes that are stateless or disposable.



========
Synopsis
========

::

    modify-volume-attribute
  [--dry-run | --no-dry-run]
  --volume-id <value>
  [--auto-enable-io | --no-auto-enable-io]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--volume-id`` (string)


  The ID of the volume.

  

``--auto-enable-io`` | ``--no-auto-enable-io`` (structure)


  Indicates whether the volume should be auto-enabled for I/O operations.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To modify a volume attribute**

This example sets the ``autoEnableIo`` attribute of the volume with the ID ``vol-1a2b3c4d`` to ``true``. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-volume-attribute --volume-id vol-1a2b3c4d --auto-enable-io


======
Output
======

None