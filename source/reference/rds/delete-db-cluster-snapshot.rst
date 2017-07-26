[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds delete-db-cluster-snapshot:


**************************
delete-db-cluster-snapshot
**************************



===========
Description
===========



Deletes a DB cluster snapshot. If the snapshot is being copied, the copy operation is terminated.

 

.. note::

   

  The DB cluster snapshot must be in the ``available`` state to be deleted.

   

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html>`_ in the *Amazon RDS User Guide.*  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DeleteDBClusterSnapshot>`_


========
Synopsis
========

::

    delete-db-cluster-snapshot
  --db-cluster-snapshot-identifier <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-cluster-snapshot-identifier`` (string)


  The identifier of the DB cluster snapshot to delete.

   

  Constraints: Must be the name of an existing DB cluster snapshot in the ``available`` state.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DBClusterSnapshot -> (structure)

  

  Contains the result of a successful invocation of the following actions:

   

   
  *  create-db-cluster-snapshot   
   
  *  delete-db-cluster-snapshot   
   

   

  This data type is used as a response element in the  describe-db-cluster-snapshots action.

  

  AvailabilityZones -> (list)

    

    Provides the list of EC2 Availability Zones that instances in the DB cluster snapshot can be restored in.

    

    (string)

      

      

    

  DBClusterSnapshotIdentifier -> (string)

    

    Specifies the identifier for the DB cluster snapshot.

    

    

  DBClusterIdentifier -> (string)

    

    Specifies the DB cluster identifier of the DB cluster that this DB cluster snapshot was created from.

    

    

  SnapshotCreateTime -> (timestamp)

    

    Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

    

    

  Engine -> (string)

    

    Specifies the name of the database engine.

    

    

  AllocatedStorage -> (integer)

    

    Specifies the allocated storage size in gigabytes (GB).

    

    

  Status -> (string)

    

    Specifies the status of this DB cluster snapshot.

    

    

  Port -> (integer)

    

    Specifies the port that the DB cluster was listening on at the time of the snapshot.

    

    

  VpcId -> (string)

    

    Provides the VPC ID associated with the DB cluster snapshot.

    

    

  ClusterCreateTime -> (timestamp)

    

    Specifies the time when the DB cluster was created, in Universal Coordinated Time (UTC).

    

    

  MasterUsername -> (string)

    

    Provides the master username for the DB cluster snapshot.

    

    

  EngineVersion -> (string)

    

    Provides the version of the database engine for this DB cluster snapshot.

    

    

  LicenseModel -> (string)

    

    Provides the license model information for this DB cluster snapshot.

    

    

  SnapshotType -> (string)

    

    Provides the type of the DB cluster snapshot.

    

    

  PercentProgress -> (integer)

    

    Specifies the percentage of the estimated data that has been transferred.

    

    

  StorageEncrypted -> (boolean)

    

    Specifies whether the DB cluster snapshot is encrypted.

    

    

  KmsKeyId -> (string)

    

    If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster snapshot.

    

    

  DBClusterSnapshotArn -> (string)

    

    The Amazon Resource Name (ARN) for the DB cluster snapshot.

    

    

  SourceDBClusterSnapshotArn -> (string)

    

    If the DB cluster snapshot was copied from a source DB cluster snapshot, the Amazon Resource Name (ARN) for the source DB cluster snapshot; otherwise, a null value.

    

    

  IAMDatabaseAuthenticationEnabled -> (boolean)

    

    True if mapping of AWS Identity and Access Management (IAM) accounts to database accounts is enabled; otherwise false.

    

    

  

