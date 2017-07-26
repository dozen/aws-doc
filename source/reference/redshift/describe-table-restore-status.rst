[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-table-restore-status:


*****************************
describe-table-restore-status
*****************************



===========
Description
===========



Lists the status of one or more table restore requests made using the  restore-table-from-cluster-snapshot API action. If you don't specify a value for the ``TableRestoreRequestId`` parameter, then ``describe-table-restore-status`` returns the status of all table restore requests ordered by the date and time of the request in ascending order. Otherwise ``describe-table-restore-status`` returns the status of the table specified by ``TableRestoreRequestId`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/DescribeTableRestoreStatus>`_


========
Synopsis
========

::

    describe-table-restore-status
  [--cluster-identifier <value>]
  [--table-restore-request-id <value>]
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-identifier`` (string)


  The Amazon Redshift cluster that the table is being restored to.

  

``--table-restore-request-id`` (string)


  The identifier of the table restore request to return status for. If you don't specify a ``TableRestoreRequestId`` value, then ``describe-table-restore-status`` returns the status of all in-progress table restore requests.

  

``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved.

  

``--marker`` (string)


  An optional pagination token provided by a previous ``describe-table-restore-status`` request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by the ``MaxRecords`` parameter.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TableRestoreStatusDetails -> (list)

  

  A list of status details for one or more table restore requests.

  

  (structure)

    

    Describes the status of a  restore-table-from-cluster-snapshot operation.

    

    TableRestoreRequestId -> (string)

      

      The unique identifier for the table restore request.

      

      

    Status -> (string)

      

      A value that describes the current state of the table restore request.

       

      Valid Values: ``SUCCEEDED`` , ``FAILED`` , ``CANCELED`` , ``PENDING`` , ``IN_PROGRESS``  

      

      

    Message -> (string)

      

      A description of the status of the table restore request. Status values include ``SUCCEEDED`` , ``FAILED`` , ``CANCELED`` , ``PENDING`` , ``IN_PROGRESS`` .

      

      

    RequestTime -> (timestamp)

      

      The time that the table restore request was made, in Universal Coordinated Time (UTC).

      

      

    ProgressInMegaBytes -> (long)

      

      The amount of data restored to the new table so far, in megabytes (MB).

      

      

    TotalDataInMegaBytes -> (long)

      

      The total amount of data to restore to the new table, in megabytes (MB).

      

      

    ClusterIdentifier -> (string)

      

      The identifier of the Amazon Redshift cluster that the table is being restored to.

      

      

    SnapshotIdentifier -> (string)

      

      The identifier of the snapshot that the table is being restored from.

      

      

    SourceDatabaseName -> (string)

      

      The name of the source database that contains the table being restored.

      

      

    SourceSchemaName -> (string)

      

      The name of the source schema that contains the table being restored.

      

      

    SourceTableName -> (string)

      

      The name of the source table being restored.

      

      

    TargetDatabaseName -> (string)

      

      The name of the database to restore the table to.

      

      

    TargetSchemaName -> (string)

      

      The name of the schema to restore the table to.

      

      

    NewTableName -> (string)

      

      The name of the table to create as a result of the table restore request.

      

      

    

  

Marker -> (string)

  

  A pagination token that can be used in a subsequent  describe-table-restore-status request.

  

  

