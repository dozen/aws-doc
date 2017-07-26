[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-snapshot-attribute:


*************************
modify-snapshot-attribute
*************************



===========
Description
===========



Adds or removes permission settings for the specified snapshot. You may add or remove specified AWS account IDs from a snapshot's list of create volume permissions, but you cannot do both in a single API call. If you need to both add and remove account IDs for a snapshot, you must use multiple API calls.

 

.. note::

   

  Encrypted snapshots and snapshots with AWS Marketplace product codes cannot be made public. Snapshots encrypted with your default CMK cannot be shared with other accounts.

   

 

For more information on modifying snapshot permissions, see `Sharing Snapshots <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-modifying-snapshot-permissions.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifySnapshotAttribute>`_


========
Synopsis
========

::

    modify-snapshot-attribute
  [--attribute <value>]
  [--create-volume-permission <value>]
  [--group-names <value>]
  [--operation-type <value>]
  --snapshot-id <value>
  [--user-ids <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attribute`` (string)


  The snapshot attribute to modify.

   

  .. note::

     

    Only volume creation permissions may be modified at the customer level.

     

  

  Possible values:

  
  *   ``productCodes``

  
  *   ``createVolumePermission``

  

  

``--create-volume-permission`` (structure)


  A JSON representation of the snapshot attribute modification.

  



Shorthand Syntax::

    Add=[{Group=string,UserId=string},{Group=string,UserId=string}],Remove=[{Group=string,UserId=string},{Group=string,UserId=string}]




JSON Syntax::

  {
    "Add": [
      {
        "Group": "all",
        "UserId": "string"
      }
      ...
    ],
    "Remove": [
      {
        "Group": "all",
        "UserId": "string"
      }
      ...
    ]
  }



``--group-names`` (list)


  The group to modify for the snapshot.

  



Syntax::

  "string" "string" ...



``--operation-type`` (string)


  The type of operation to perform to the attribute.

  

  Possible values:

  
  *   ``add``

  
  *   ``remove``

  

  

``--snapshot-id`` (string)


  The ID of the snapshot.

  

``--user-ids`` (list)


  The account ID to modify for the snapshot.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To modify a snapshot attribute**

This example modifies snapshot ``snap-1234567890abcdef0`` to remove the create volume permission for a user with the account ID ``123456789012``. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-snapshot-attribute --snapshot-id snap-1234567890abcdef0 --attribute createVolumePermission --operation-type remove --user-ids 123456789012

**To make a snapshot public**

This example makes the snapshot ``snap-1234567890abcdef0`` public.

Command::

  aws ec2 modify-snapshot-attribute --snapshot-id snap-1234567890abcdef0 --attribute createVolumePermission --operation-type add --group-names all

======
Output
======

None