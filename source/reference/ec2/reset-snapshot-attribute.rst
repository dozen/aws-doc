[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 reset-snapshot-attribute:


************************
reset-snapshot-attribute
************************



===========
Description
===========



Resets permission settings for the specified snapshot.

 

For more information on modifying snapshot permissions, see `Sharing Snapshots`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    reset-snapshot-attribute
  [--dry-run | --no-dry-run]
  --snapshot-id <value>
  --attribute <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--snapshot-id`` (string)


  The ID of the snapshot.

  

``--attribute`` (string)


  The attribute to reset. Currently, only the attribute for permission to create volumes can be reset.

  

  Possible values:

  
  *   ``productCodes``

  
  *   ``createVolumePermission``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To reset a snapshot attribute**

This example resets the create volume permissions for snapshot ``snap-1a2b3c4d``. If the command succeeds, no output is returned.

Command::

  aws ec2 reset-snapshot-attribute --snapshot-id snap-1a2b3c4d --attribute createVolumePermission



======
Output
======

None

.. _Sharing Snapshots: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-modifying-snapshot-permissions.html
