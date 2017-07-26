[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-cluster-snapshots:


*****************************
describe-db-cluster-snapshots
*****************************



===========
Description
===========



Returns information about DB cluster snapshots. This API supports pagination. 

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.* 



========
Synopsis
========

::

    describe-db-cluster-snapshots
  [--db-cluster-identifier <value>]
  [--db-cluster-snapshot-identifier <value>]
  [--snapshot-type <value>]
  [--filters <value>]
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-cluster-identifier`` (string)


  A DB cluster identifier to retrieve the list of DB cluster snapshots for. This parameter cannot be used in conjunction with the ``DBClusterSnapshotIdentifier`` parameter. This parameter is not case-sensitive. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--db-cluster-snapshot-identifier`` (string)


  A specific DB cluster snapshot identifier to describe. This parameter cannot be used in conjunction with the ``DBClusterIdentifier`` parameter. This value is stored as a lowercase string. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   
  * If this is the identifier of an automated snapshot, the ``SnapshotType`` parameter must also be specified.
   

  

``--snapshot-type`` (string)


  The type of DB cluster snapshots that will be returned. Values can be ``automated`` or ``manual`` . If this parameter is not specified, the returned results will include all snapshot types. 

  

``--filters`` (list)


  This parameter is not currently supported.

  



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



``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

   

  Default: 100

   

  Constraints: Minimum 20, maximum 100.

  

``--marker`` (string)


  An optional pagination token provided by a previous ``describe-db-cluster-snapshots`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous  describe-db-cluster-snapshots request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

DBClusterSnapshots -> (list)

  

  Provides a list of DB cluster snapshots for the user. 

  

  (structure)

    

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
