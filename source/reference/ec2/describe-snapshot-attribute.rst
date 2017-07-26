[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-snapshot-attribute:


***************************
describe-snapshot-attribute
***************************



===========
Description
===========



Describes the specified attribute of the specified snapshot. You can specify only one attribute at a time.

 

For more information about EBS snapshots, see `Amazon EBS Snapshots <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeSnapshotAttribute>`_


========
Synopsis
========

::

    describe-snapshot-attribute
  --attribute <value>
  --snapshot-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attribute`` (string)


  The snapshot attribute you would like to view.

  

  Possible values:

  
  *   ``productCodes``

  
  *   ``createVolumePermission``

  

  

``--snapshot-id`` (string)


  The ID of the EBS snapshot.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe snapshot attributes**

This example command describes the ``createVolumePermission`` attribute on a snapshot with the snapshot ID of ``snap-066877671789bd71b``.

Command::

  aws ec2 describe-snapshot-attribute --snapshot-id snap-066877671789bd71b --attribute createVolumePermission

Output::

   {
       "SnapshotId": "snap-066877671789bd71b",
       "CreateVolumePermissions": []
   }

======
Output
======

CreateVolumePermissions -> (list)

  

  A list of permissions for creating volumes from the snapshot.

  

  (structure)

    

    Describes the user or group to be added or removed from the permissions for a volume.

    

    Group -> (string)

      

      The specific group that is to be added or removed from a volume's list of create volume permissions.

      

      

    UserId -> (string)

      

      The specific AWS account ID that is to be added or removed from a volume's list of create volume permissions.

      

      

    

  

ProductCodes -> (list)

  

  A list of product codes.

  

  (structure)

    

    Describes a product code.

    

    ProductCodeId -> (string)

      

      The product code.

      

      

    ProductCodeType -> (string)

      

      The type of product code.

      

      

    

  

SnapshotId -> (string)

  

  The ID of the EBS snapshot.

  

  

