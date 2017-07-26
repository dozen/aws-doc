[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds copy-db-cluster-snapshot:


************************
copy-db-cluster-snapshot
************************



===========
Description
===========



Creates a snapshot of a DB cluster. For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.* 



========
Synopsis
========

::

    copy-db-cluster-snapshot
  --source-db-cluster-snapshot-identifier <value>
  --target-db-cluster-snapshot-identifier <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--source-db-cluster-snapshot-identifier`` (string)


  The identifier of the DB cluster snapshot to copy. This parameter is not case-sensitive. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens.
   
  * First character must be a letter.
   
  * Cannot end with a hyphen or contain two consecutive hyphens.
   

   

  Example: ``my-cluster-snapshot1`` 

  

``--target-db-cluster-snapshot-identifier`` (string)


  The identifier of the new DB cluster snapshot to create from the source DB cluster snapshot. This parameter is not case-sensitive. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens.
   
  * First character must be a letter.
   
  * Cannot end with a hyphen or contain two consecutive hyphens.
   

   

  Example: ``my-cluster-snapshot2`` 

  

``--tags`` (list)


  A list of tags.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    

  



.. _Aurora on Amazon RDS: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html
