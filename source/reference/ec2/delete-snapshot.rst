[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-snapshot:


***************
delete-snapshot
***************



===========
Description
===========



Deletes the specified snapshot.

 

When you make periodic snapshots of a volume, the snapshots are incremental, and only the blocks on the device that have changed since your last snapshot are saved in the new snapshot. When you delete a snapshot, only the data not needed for any other snapshot is removed. So regardless of which prior snapshots have been deleted, all active snapshots will have access to all the information needed to restore the volume.

 

You cannot delete a snapshot of the root device of an EBS volume used by a registered AMI. You must first de-register the AMI before you can delete the snapshot.

 

For more information, see `Deleting an Amazon EBS Snapshot`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    delete-snapshot
  [--dry-run | --no-dry-run]
  --snapshot-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--snapshot-id`` (string)


  The ID of the EBS snapshot.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a snapshot**

This example command deletes a snapshot with the snapshot ID of ``snap-1234abcd``. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-snapshot --snapshot-id snap-1234abcd


======
Output
======

None

.. _Deleting an Amazon EBS Snapshot: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-deleting-snapshot.html
