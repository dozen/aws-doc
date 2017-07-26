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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifyVolumeAttribute>`_


========
Synopsis
========

::

    modify-volume-attribute
  [--auto-enable-io | --no-auto-enable-io]
  --volume-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-enable-io`` | ``--no-auto-enable-io`` (structure)


  Indicates whether the volume should be auto-enabled for I/O operations.

  

``--volume-id`` (string)


  The ID of the volume.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To modify a volume attribute**

This example sets the ``autoEnableIo`` attribute of the volume with the ID ``vol-1234567890abcdef0`` to ``true``. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-volume-attribute --volume-id vol-1234567890abcdef0 --auto-enable-io


======
Output
======

None