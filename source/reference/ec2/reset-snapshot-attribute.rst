[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 reset-snapshot-attribute:


************************
reset-snapshot-attribute
************************



===========
Description
===========



Resets permission settings for the specified snapshot.

 

For more information on modifying snapshot permissions, see `Sharing Snapshots <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-modifying-snapshot-permissions.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ResetSnapshotAttribute>`_


========
Synopsis
========

::

    reset-snapshot-attribute
  --attribute <value>
  --snapshot-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attribute`` (string)


  The attribute to reset. Currently, only the attribute for permission to create volumes can be reset.

  

  Possible values:

  
  *   ``productCodes``

  
  *   ``createVolumePermission``

  

  

``--snapshot-id`` (string)


  The ID of the snapshot.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To reset a snapshot attribute**

This example resets the create volume permissions for snapshot ``snap-1234567890abcdef0``. If the command succeeds, no output is returned.

Command::

  aws ec2 reset-snapshot-attribute --snapshot-id snap-1234567890abcdef0 --attribute createVolumePermission



======
Output
======

None