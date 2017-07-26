[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-snapshots:


*********************
describe-db-snapshots
*********************



===========
Description
===========



Returns information about DB snapshots. This API supports pagination. 



``describe-db-snapshots`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DBSnapshots``


========
Synopsis
========

::

    describe-db-snapshots
  [--db-instance-identifier <value>]
  [--db-snapshot-identifier <value>]
  [--snapshot-type <value>]
  [--filters <value>]
  [--include-shared | --no-include-shared]
  [--include-public | --no-include-public]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-instance-identifier`` (string)


  A DB instance identifier to retrieve the list of DB snapshots for. This parameter cannot be used in conjunction with ``DBSnapshotIdentifier`` . This parameter is not case-sensitive. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--db-snapshot-identifier`` (string)


  A specific DB snapshot identifier to describe. This parameter cannot be used in conjunction with ``DBInstanceIdentifier`` . This value is stored as a lowercase string. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters.
   
  * First character must be a letter.
   
  * Cannot end with a hyphen or contain two consecutive hyphens.
   
  * If this is the identifier of an automated snapshot, the ``SnapshotType`` parameter must also be specified.
   

  

``--snapshot-type`` (string)


  The type of snapshots that will be returned. You can specify one of the following values:

   

   
  * ``automated`` - Return all DB snapshots that have been automatically taken by Amazon RDS for my AWS account.
   
  * ``manual`` - Return all DB snapshots that have been taken by my AWS account.
   
  * ``shared`` - Return all manual DB snapshots that have been shared to my AWS account.
   
  * ``public`` - Return all DB snapshots that have been marked as public.
   

   

  If you do not specify a ``SnapshotType`` , then both automated and manual snapshots are returned. You can include shared snapshots with these results by setting the ``IncludeShared`` parameter to ``true`` . You can include public snapshots with these results by setting the ``IncludePublic`` parameter to ``true`` .

   

  The ``IncludeShared`` and ``IncludePublic`` parameters do not apply for ``SnapshotType`` values of ``manual`` or ``automated`` . The ``IncludePublic`` parameter does not apply when ``SnapshotType`` is set to ``shared`` . the ``IncludeShared`` parameter does not apply when ``SnapshotType`` is set to ``public`` .

  

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



``--include-shared`` | ``--no-include-shared`` (boolean)


  True to include shared manual DB snapshots from other AWS accounts that this AWS account has been given permission to copy or restore; otherwise false. The default is false.

   

  An AWS account is given permission to restore a manual DB snapshot from another AWS account by the  modify-db-snapshot-attribute API.

  

``--include-public`` | ``--no-include-public`` (boolean)


  True to include manual DB snapshots that are public and can be copied or restored by any AWS account; otherwise false. The default is false.

   

  An manual DB snapshot is shared as public by the  modify-db-snapshot-attribute API.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

DBSnapshots -> (list)

  

  A list of  DBSnapshot instances. 

  

  (structure)

    

    Contains the result of a successful invocation of the following actions: 

     

     
    *  create-db-snapshot  
     
    *  delete-db-snapshot  
     

     

    This data type is used as a response element in the  describe-db-snapshots action.

    

    DBSnapshotIdentifier -> (string)

      

      Specifies the identifier for the DB snapshot. 

      

      

    DBInstanceIdentifier -> (string)

      

      Specifies the DB instance identifier of the DB instance this DB snapshot was created from. 

      

      

    SnapshotCreateTime -> (timestamp)

      

      Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC). 

      

      

    Engine -> (string)

      

      Specifies the name of the database engine. 

      

      

    AllocatedStorage -> (integer)

      

      Specifies the allocated storage size in gigabytes (GB). 

      

      

    Status -> (string)

      

      Specifies the status of this DB snapshot. 

      

      

    Port -> (integer)

      

      Specifies the port that the database engine was listening on at the time of the snapshot. 

      

      

    AvailabilityZone -> (string)

      

      Specifies the name of the Availability Zone the DB instance was located in at the time of the DB snapshot. 

      

      

    VpcId -> (string)

      

      Provides the VPC ID associated with the DB snapshot. 

      

      

    InstanceCreateTime -> (timestamp)

      

      Specifies the time when the snapshot was taken, in Universal Coordinated Time (UTC). 

      

      

    MasterUsername -> (string)

      

      Provides the master username for the DB snapshot. 

      

      

    EngineVersion -> (string)

      

      Specifies the version of the database engine. 

      

      

    LicenseModel -> (string)

      

      License model information for the restored DB instance. 

      

      

    SnapshotType -> (string)

      

      Provides the type of the DB snapshot. 

      

      

    Iops -> (integer)

      

      Specifies the Provisioned IOPS (I/O operations per second) value of the DB instance at the time of the snapshot. 

      

      

    OptionGroupName -> (string)

      

      Provides the option group name for the DB snapshot. 

      

      

    PercentProgress -> (integer)

      

      The percentage of the estimated data that has been transferred. 

      

      

    SourceRegion -> (string)

      

      The region that the DB snapshot was created in or copied from. 

      

      

    SourceDBSnapshotIdentifier -> (string)

      

      The DB snapshot Arn that the DB snapshot was copied from. It only has value in case of cross customer or cross region copy. 

      

      

    StorageType -> (string)

      

      Specifies the storage type associated with DB Snapshot. 

      

      

    TdeCredentialArn -> (string)

      

      The ARN from the Key Store with which to associate the instance for TDE encryption. 

      

      

    Encrypted -> (boolean)

      

      Specifies whether the DB snapshot is encrypted. 

      

      

    KmsKeyId -> (string)

      

      If ``Encrypted`` is true, the KMS key identifier for the encrypted DB snapshot. 

      

      

    

  

