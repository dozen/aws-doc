[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift revoke-snapshot-access:


**********************
revoke-snapshot-access
**********************



===========
Description
===========



Removes the ability of the specified AWS customer account to restore the specified snapshot. If the account is currently restoring the snapshot, the restore will run to completion. 

 

For more information about working with snapshots, go to `Amazon Redshift Snapshots`_ in the *Amazon Redshift Cluster Management Guide* . 



========
Synopsis
========

::

    revoke-snapshot-access
  --snapshot-identifier <value>
  [--snapshot-cluster-identifier <value>]
  --account-with-restore-access <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--snapshot-identifier`` (string)


  The identifier of the snapshot that the account can no longer access. 

  

``--snapshot-cluster-identifier`` (string)


  The identifier of the cluster the snapshot was created from. This parameter is required if your IAM user has a policy containing a snapshot resource element that specifies anything other than * for the cluster name. 

  

``--account-with-restore-access`` (string)


  The identifier of the AWS customer account that can no longer restore the specified snapshot. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Revoke the Authorization of an AWS Account to Restore a Snapshot
----------------------------------------------------------------

This example revokes the authorization of the AWS account ``444455556666`` to
restore the snapshot ``my-snapshot-id``. By default, the output is in JSON
format.

Command::

   aws redshift revoke-snapshot-access --snapshot-id my-snapshot-id --account-with-restore-access 444455556666

Result::

    {
       "Snapshot": {
          "Status": "available",
          "SnapshotCreateTime": "2013-07-17T22:04:18.947Z",
          "EstimatedSecondsToCompletion": 0,
          "AvailabilityZone": "us-east-1a",
          "ClusterVersion": "1.0",
          "MasterUsername": "adminuser",
          "Encrypted": false,
          "OwnerAccount": "111122223333",
          "BackupProgressInMegabytes": 11.0,
          "ElapsedTimeInSeconds": 0,
          "DBName": "dev",
          "CurrentBackupRateInMegabytesPerSecond: 0.1534,
          "ClusterCreateTime": "2013-01-22T21:59:29.559Z",
          "ActualIncrementalBackupSizeInMegabytes"; 11.0,
          "SnapshotType": "manual",
          "NodeType": "dw.hs1.xlarge",
          "ClusterIdentifier": "mycluster",
          "TotalBackupSizeInMegabytes": 20.0,
          "Port": 5439,
          "NumberOfNodes": 2,
          "SnapshotIdentifier": "my-snapshot-id"
       }
    }



======
Output
======

Snapshot -> (structure)

  

  Describes a snapshot.

  

  SnapshotIdentifier -> (string)

    

    The snapshot identifier that is provided in the request. 

    

    

  ClusterIdentifier -> (string)

    

    The identifier of the cluster for which the snapshot was taken. 

    

    

  SnapshotCreateTime -> (timestamp)

    

    The time (UTC) when Amazon Redshift began the snapshot. A snapshot contains a copy of the cluster data as of this exact time. 

    

    

  Status -> (string)

    

    The snapshot status. The value of the status depends on the API operation used. 

     
    *  create-cluster-snapshot and  copy-cluster-snapshot returns status as "creating". 
     
    *  describe-cluster-snapshots returns status as "creating", "available", "final snapshot", or "failed".
     
    *  delete-cluster-snapshot returns status as "deleted".
     

     

    

    

  Port -> (integer)

    

    The port that the cluster is listening on. 

    

    

  AvailabilityZone -> (string)

    

    The Availability Zone in which the cluster was created. 

    

    

  ClusterCreateTime -> (timestamp)

    

    The time (UTC) when the cluster was originally created. 

    

    

  MasterUsername -> (string)

    

    The master user name for the cluster. 

    

    

  ClusterVersion -> (string)

    

    The version ID of the Amazon Redshift engine that is running on the cluster. 

    

    

  SnapshotType -> (string)

    

    The snapshot type. Snapshots created using  create-cluster-snapshot and  copy-cluster-snapshot will be of type "manual". 

    

    

  NodeType -> (string)

    

    The node type of the nodes in the cluster.

    

    

  NumberOfNodes -> (integer)

    

    The number of nodes in the cluster.

    

    

  DBName -> (string)

    

    The name of the database that was created when the cluster was created. 

    

    

  VpcId -> (string)

    

    The VPC identifier of the cluster if the snapshot is from a cluster in a VPC. Otherwise, this field is not in the output.

    

    

  Encrypted -> (boolean)

    

    If ``true`` , the data in the snapshot is encrypted at rest.

    

    

  KmsKeyId -> (string)

    

    The AWS Key Management Service (KMS) key ID of the encryption key that was used to encrypt data in the cluster from which the snapshot was taken.

    

    

  EncryptedWithHSM -> (boolean)

    

    A boolean that indicates whether the snapshot data is encrypted using the HSM keys of the source cluster. ``true`` indicates that the data is encrypted using HSM keys.

    

    

  AccountsWithRestoreAccess -> (list)

    

    A list of the AWS customer accounts authorized to restore the snapshot. Returns ``null`` if no accounts are authorized. Visible only to the snapshot owner. 

    

    (structure)

      

      Describes an AWS customer account authorized to restore a snapshot. 

      

      AccountId -> (string)

        

        The identifier of an AWS customer account authorized to restore a snapshot. 

        

        

      

    

  OwnerAccount -> (string)

    

    For manual snapshots, the AWS customer account used to create or copy the snapshot. For automatic snapshots, the owner of the cluster. The owner can perform all snapshot actions, such as sharing a manual snapshot. 

    

    

  TotalBackupSizeInMegaBytes -> (double)

    

    The size of the complete set of backup data that would be used to restore the cluster. 

    

    

  ActualIncrementalBackupSizeInMegaBytes -> (double)

    

    The size of the incremental backup. 

    

    

  BackupProgressInMegaBytes -> (double)

    

    The number of megabytes that have been transferred to the snapshot backup. 

    

    

  CurrentBackupRateInMegaBytesPerSecond -> (double)

    

    The number of megabytes per second being transferred to the snapshot backup. Returns ``0`` for a completed backup. 

    

    

  EstimatedSecondsToCompletion -> (long)

    

    The estimate of the time remaining before the snapshot backup will complete. Returns ``0`` for a completed backup. 

    

    

  ElapsedTimeInSeconds -> (long)

    

    The amount of time an in-progress snapshot backup has been running, or the amount of time it took a completed backup to finish. 

    

    

  SourceRegion -> (string)

    

    The source region from which the snapshot was copied. 

    

    

  Tags -> (list)

    

    The list of tags for the cluster snapshot.

    

    (structure)

      

      A tag consisting of a name/value pair for a resource.

      

      Key -> (string)

        

        The key, or name, for the resource tag.

        

        

      Value -> (string)

        

        The value for the resource tag.

        

        

      

    

  RestorableNodeTypes -> (list)

    

    The list of node types that this cluster snapshot is able to restore into.

    

    (string)

      

      

    

  



.. _Amazon Redshift Snapshots: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-snapshots.html
