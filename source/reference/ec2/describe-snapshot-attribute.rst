[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-snapshot-attribute:


***************************
describe-snapshot-attribute
***************************



===========
Description
===========



Describes the specified attribute of the specified snapshot. You can specify only one attribute at a time.

 

For more information about EBS snapshots, see `Amazon EBS Snapshots`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    describe-snapshot-attribute
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


  The ID of the EBS snapshot.

  

``--attribute`` (string)


  The snapshot attribute you would like to view.

  

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

**To describe snapshot attributes**

This example command describes the ``createVolumePermission`` and ``productCodes`` attributes on a snapshot with the snapshot ID of ``snap-1234abcd``.

Command::

  aws ec2 describe-snapshot-attribute --snapshot-id snap-1234abcd --attribute createVolumePermission --attribute productCodes

Output::

   {
       "SnapshotId": "snap-b52c0044",
       "CreateVolumePermissions": [],
       "ProductCodes": []
   }

======
Output
======

SnapshotId -> (string)

  

  The ID of the EBS snapshot.

  

  

CreateVolumePermissions -> (list)

  

  A list of permissions for creating volumes from the snapshot.

  

  (structure)

    

    Describes the user or group to be added or removed from the permissions for a volume.

    

    UserId -> (string)

      

      The specific AWS account ID that is to be added or removed from a volume's list of create volume permissions.

      

      

    Group -> (string)

      

      The specific group that is to be added or removed from a volume's list of create volume permissions.

      

      

    

  

ProductCodes -> (list)

  

  A list of product codes.

  

  (structure)

    

    Describes a product code.

    

    ProductCodeId -> (string)

      

      The product code.

      

      

    ProductCodeType -> (string)

      

      The type of product code.

      

      

    

  



.. _Amazon EBS Snapshots: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html
