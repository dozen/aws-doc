[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-snapshot-attribute:


*************************
modify-snapshot-attribute
*************************



===========
Description
===========



Adds or removes permission settings for the specified snapshot. You may add or remove specified AWS account IDs from a snapshot's list of create volume permissions, but you cannot do both in a single API call. If you need to both add and remove account IDs for a snapshot, you must use multiple API calls.

 

For more information on modifying snapshot permissions, see `Sharing Snapshots`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

.. note::

   

  Snapshots with AWS Marketplace product codes cannot be made public.

   



========
Synopsis
========

::

    modify-snapshot-attribute
  [--dry-run | --no-dry-run]
  --snapshot-id <value>
  [--attribute <value>]
  [--operation-type <value>]
  [--user-ids <value>]
  [--group-names <value>]
  [--create-volume-permission <value>]
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


  The snapshot attribute to modify.

   

  .. note::

     

    Only volume creation permissions may be modified at the customer level.

     

  

  Possible values:

  
  *   ``productCodes``

  
  *   ``createVolumePermission``

  

  

``--operation-type`` (string)


  The type of operation to perform to the attribute.

  

  Possible values:

  
  *   ``add``

  
  *   ``remove``

  

  

``--user-ids`` (list)


  The account ID to modify for the snapshot.

  



Syntax::

  "string" "string" ...



``--group-names`` (list)


  The group to modify for the snapshot.

  



Syntax::

  "string" "string" ...



``--create-volume-permission`` (structure)


  A JSON representation of the snapshot attribute modification.

  



Shorthand Syntax::

    Add=[{UserId=string,Group=string},{UserId=string,Group=string}],Remove=[{UserId=string,Group=string},{UserId=string,Group=string}]




JSON Syntax::

  {
    "Add": [
      {
        "UserId": "string",
        "Group": "all"
      }
      ...
    ],
    "Remove": [
      {
        "UserId": "string",
        "Group": "all"
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To modify a snapshot attribute**

This example modifies snapshot ``snap-1a2b3c4d`` to remove the create volume permission for a user with the account ID ``123456789012``. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-snapshot-attribute --snapshot-id snap-1a2b3c4d --attribute createVolumePermission --operation-type remove --user-ids 123456789012

**To make a snapshot public**

This example makes the snapshot ``snap-1a2b3c4d`` public.

Command::

  aws ec2 modify-snapshot-attribute --snapshot-id snap-1a2b3c4d --attribute createVolumePermission --operation-type add --group-names all

======
Output
======

None

.. _Sharing Snapshots: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-modifying-snapshot-permissions.html
