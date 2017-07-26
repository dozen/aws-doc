[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 enable-volume-io:


****************
enable-volume-io
****************



===========
Description
===========



Enables I/O operations for a volume that had I/O operations disabled because the data on the volume was potentially inconsistent.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/EnableVolumeIO>`_


========
Synopsis
========

::

    enable-volume-io
  [--dry-run | --no-dry-run]
  --volume-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--volume-id`` (string)


  The ID of the volume.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To enable I/O for a volume**

This example enables I/O on volume ``vol-1234567890abcdef0``.

Command::

  aws ec2 enable-volume-io --volume-id vol-1234567890abcdef0
  
Output::

  {
    "Return": true
  }

======
Output
======

None