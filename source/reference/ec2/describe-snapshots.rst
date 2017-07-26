[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-snapshots:


******************
describe-snapshots
******************



===========
Description
===========



Describes one or more of the EBS snapshots available to you. Available snapshots include public snapshots available for any AWS account to launch, private snapshots that you own, and private snapshots owned by another AWS account but for which you've been given explicit create volume permissions.

 

The create volume permissions fall into the following categories:

 

 
* *public* : The owner of the snapshot granted create volume permissions for the snapshot to the ``all`` group. All AWS accounts have create volume permissions for these snapshots. 
 
* *explicit* : The owner of the snapshot granted create volume permissions to a specific AWS account. 
 
* *implicit* : An AWS account has implicit create volume permissions for all snapshots it owns. 
 

 

The list of snapshots returned can be modified by specifying snapshot IDs, snapshot owners, or AWS accounts with create volume permissions. If no options are specified, Amazon EC2 returns all snapshots for which you have create volume permissions.

 

If you specify one or more snapshot IDs, only snapshots that have the specified IDs are returned. If you specify an invalid snapshot ID, an error is returned. If you specify a snapshot ID for which you do not have access, it is not included in the returned results.

 

If you specify one or more snapshot owners using the ``OwnerIds`` option, only snapshots from the specified owners and for which you have access are returned. The results can include the AWS account IDs of the specified owners, ``amazon`` for snapshots owned by Amazon, or ``self`` for snapshots that you own.

 

If you specify a list of restorable users, only snapshots with create snapshot permissions for those users are returned. You can specify AWS account IDs (if you own the snapshots), ``self`` for snapshots for which you own or have explicit permissions, or ``all`` for public snapshots.

 

If you are describing a long list of snapshots, you can paginate the output to make the list more manageable. The ``MaxResults`` parameter sets the maximum number of results returned in a single page. If the list of results exceeds your ``MaxResults`` value, then that number of results is returned along with a ``NextToken`` value that can be passed to a subsequent ``describe-snapshots`` request to retrieve the remaining results.

 

For more information about EBS snapshots, see `Amazon EBS Snapshots <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeSnapshots>`_


``describe-snapshots`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Snapshots``


========
Synopsis
========

::

    describe-snapshots
  [--filters <value>]
  [--owner-ids <value>]
  [--restorable-by-user-ids <value>]
  [--snapshot-ids <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``description`` - A description of the snapshot. 
   
  * ``owner-alias`` - Value from an Amazon-maintained list (``amazon`` | ``aws-marketplace`` | ``microsoft`` ) of snapshot owners. Not to be confused with the user-configured AWS account alias, which is set from the IAM console. 
   
  * ``owner-id`` - The ID of the AWS account that owns the snapshot. 
   
  * ``progress`` - The progress of the snapshot, as a percentage (for example, 80%). 
   
  * ``snapshot-id`` - The snapshot ID. 
   
  * ``start-time`` - The time stamp when the snapshot was initiated. 
   
  * ``status`` - The status of the snapshot (``pending`` | ``completed`` | ``error`` ). 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``volume-id`` - The ID of the volume the snapshot is for. 
   
  * ``volume-size`` - The size of the volume, in GiB. 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--owner-ids`` (list)


  Returns the snapshots owned by the specified owner. Multiple owners can be specified.

  



Syntax::

  "string" "string" ...



``--restorable-by-user-ids`` (list)


  One or more AWS accounts IDs that can create volumes from the snapshot.

  



Syntax::

  "string" "string" ...



``--snapshot-ids`` (list)


  One or more snapshot IDs.

   

  Default: Describes snapshots for which you have launch permissions.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a snapshot**

This example command describes a snapshot with the snapshot ID of ``snap-1234567890abcdef0``.

Command::

  aws ec2 describe-snapshots --snapshot-id snap-1234567890abcdef0

Output::

   {
       "Snapshots": [
           {
               "Description": "This is my snapshot.",
               "VolumeId": "vol-049df61146c4d7901",
               "State": "completed",
               "VolumeSize": 8,
               "Progress": "100%",
               "StartTime": "2014-02-28T21:28:32.000Z",
               "SnapshotId": "snap-1234567890abcdef0",
               "OwnerId": "012345678910"
           }
       ]
   }

**To describe snapshots using filters**

This example command describes all snapshots owned by the ID 012345678910 that are in the ``pending`` status.

Command::

  aws ec2 describe-snapshots --owner-ids 012345678910 --filters Name=status,Values=pending

Output::

   {
       "Snapshots": [
           {
               "Description": "This is my copied snapshot.",
               "VolumeId": "vol-1234567890abcdef0",
               "State": "pending",
               "VolumeSize": 8,
               "Progress": "87%",
               "StartTime": "2014-02-28T21:37:27.000Z",
               "SnapshotId": "snap-066877671789bd71b",
               "OwnerId": "012345678910"
           }
       ]
   }

**To describe tagged snapshots and filter the output**

This example command describes all snapshots that have the tag ``Group=Prod``. The output is filtered to display only the snapshot IDs and the time the snapshot was started.

Command::

  aws ec2 describe-snapshots --filters Name=tag-key,Values="Group" Name=tag-value,Values="Prod" --query 'Snapshots[*].{ID:SnapshotId,Time:StartTime}'

Output::

   [
     {
        "ID": "snap-1234567890abcdef0", 
        "Time": "2014-08-04T12:48:18.000Z"
     }
   ]

======
Output
======

Snapshots -> (list)

  

  Information about the snapshots.

  

  (structure)

    

    Describes a snapshot.

    

    DataEncryptionKeyId -> (string)

      

      The data encryption key identifier for the snapshot. This value is a unique identifier that corresponds to the data encryption key that was used to encrypt the original volume or snapshot copy. Because data encryption keys are inherited by volumes created from snapshots, and vice versa, if snapshots share the same data encryption key identifier, then they belong to the same volume/snapshot lineage. This parameter is only returned by the  describe-snapshots API operation.

      

      

    Description -> (string)

      

      The description for the snapshot.

      

      

    Encrypted -> (boolean)

      

      Indicates whether the snapshot is encrypted.

      

      

    KmsKeyId -> (string)

      

      The full ARN of the AWS Key Management Service (AWS KMS) customer master key (CMK) that was used to protect the volume encryption key for the parent volume.

      

      

    OwnerId -> (string)

      

      The AWS account ID of the EBS snapshot owner.

      

      

    Progress -> (string)

      

      The progress of the snapshot, as a percentage.

      

      

    SnapshotId -> (string)

      

      The ID of the snapshot. Each snapshot receives a unique identifier when it is created.

      

      

    StartTime -> (timestamp)

      

      The time stamp when the snapshot was initiated.

      

      

    State -> (string)

      

      The snapshot state.

      

      

    StateMessage -> (string)

      

      Encrypted Amazon EBS snapshots are copied asynchronously. If a snapshot copy operation fails (for example, if the proper AWS Key Management Service (AWS KMS) permissions are not obtained) this field displays error state details to help you diagnose why the error occurred. This parameter is only returned by the  describe-snapshots API operation.

      

      

    VolumeId -> (string)

      

      The ID of the volume that was used to create the snapshot. Snapshots created by the  copy-snapshot action have an arbitrary volume ID that should not be used for any purpose.

      

      

    VolumeSize -> (integer)

      

      The size of the volume, in GiB.

      

      

    OwnerAlias -> (string)

      

      Value from an Amazon-maintained list (``amazon`` | ``aws-marketplace`` | ``microsoft`` ) of snapshot owners. Not to be confused with the user-configured AWS account alias, which is set from the IAM console. 

      

      

    Tags -> (list)

      

      Any tags assigned to the snapshot.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag.

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    

  

NextToken -> (string)

  

  The ``NextToken`` value to include in a future ``describe-snapshots`` request. When the results of a ``describe-snapshots`` request exceed ``MaxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

