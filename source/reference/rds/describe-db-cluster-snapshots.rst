[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-cluster-snapshots:


*****************************
describe-db-cluster-snapshots
*****************************



===========
Description
===========



Returns information about DB cluster snapshots. This API action supports pagination.

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html>`_ in the *Amazon RDS User Guide.*  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeDBClusterSnapshots>`_


``describe-db-cluster-snapshots`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DBClusterSnapshots``


========
Synopsis
========

::

    describe-db-cluster-snapshots
  [--db-cluster-identifier <value>]
  [--db-cluster-snapshot-identifier <value>]
  [--snapshot-type <value>]
  [--filters <value>]
  [--include-shared | --no-include-shared]
  [--include-public | --no-include-public]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-cluster-identifier`` (string)


  The ID of the DB cluster to retrieve the list of DB cluster snapshots for. This parameter cannot be used in conjunction with the ``DBClusterSnapshotIdentifier`` parameter. This parameter is not case-sensitive. 

   

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
   
  * If this identifier is for an automated snapshot, the ``SnapshotType`` parameter must also be specified. 
   

  

``--snapshot-type`` (string)


  The type of DB cluster snapshots to be returned. You can specify one of the following values:

   

   
  * ``automated`` - Return all DB cluster snapshots that have been automatically taken by Amazon RDS for my AWS account. 
   
  * ``manual`` - Return all DB cluster snapshots that have been taken by my AWS account. 
   
  * ``shared`` - Return all manual DB cluster snapshots that have been shared to my AWS account. 
   
  * ``public`` - Return all DB cluster snapshots that have been marked as public. 
   

   

  If you don't specify a ``SnapshotType`` value, then both automated and manual DB cluster snapshots are returned. You can include shared DB cluster snapshots with these results by setting the ``IncludeShared`` parameter to ``true`` . You can include public DB cluster snapshots with these results by setting the ``IncludePublic`` parameter to ``true`` .

   

  The ``IncludeShared`` and ``IncludePublic`` parameters don't apply for ``SnapshotType`` values of ``manual`` or ``automated`` . The ``IncludePublic`` parameter doesn't apply when ``SnapshotType`` is set to ``shared`` . The ``IncludeShared`` parameter doesn't apply when ``SnapshotType`` is set to ``public`` .

  

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


  Set this value to ``true`` to include shared manual DB cluster snapshots from other AWS accounts that this AWS account has been given permission to copy or restore, otherwise set this value to ``false`` . The default is ``false`` .

   

  You can give an AWS account permission to restore a manual DB cluster snapshot from another AWS account by the  modify-db-cluster-snapshot-attribute API action.

  

``--include-public`` | ``--no-include-public`` (boolean)


  Set this value to ``true`` to include manual DB cluster snapshots that are public and can be copied or restored by any AWS account, otherwise set this value to ``false`` . The default is ``false`` . The default is false.

   

  You can share a manual DB cluster snapshot as public by using the  modify-db-cluster-snapshot-attribute API action.

  

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

      

      

    DBClusterSnapshotArn -> (string)

      

      The Amazon Resource Name (ARN) for the DB cluster snapshot.

      

      

    SourceDBClusterSnapshotArn -> (string)

      

      If the DB cluster snapshot was copied from a source DB cluster snapshot, the Amazon Resource Name (ARN) for the source DB cluster snapshot; otherwise, a null value.

      

      

    IAMDatabaseAuthenticationEnabled -> (boolean)

      

      True if mapping of AWS Identity and Access Management (IAM) accounts to database accounts is enabled; otherwise false.

      

      

    

  

