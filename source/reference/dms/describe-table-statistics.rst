[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms describe-table-statistics:


*************************
describe-table-statistics
*************************



===========
Description
===========



Returns table statistics on the database migration task, including table name, rows inserted, rows updated, and rows deleted.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/DescribeTableStatistics>`_


========
Synopsis
========

::

    describe-table-statistics
  --replication-task-arn <value>
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-task-arn`` (string)


  The Amazon Resource Name (ARN) of the replication task.

  

``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

   

  Default: 100

   

  Constraints: Minimum 20, maximum 100.

  

``--marker`` (string)


  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ReplicationTaskArn -> (string)

  

  The Amazon Resource Name (ARN) of the replication task.

  

  

TableStatistics -> (list)

  

  The table statistics.

  

  (structure)

    

    

    

    SchemaName -> (string)

      

      The schema name.

      

      

    TableName -> (string)

      

      The name of the table.

      

      

    Inserts -> (long)

      

      The number of insert actions performed on a table.

      

      

    Deletes -> (long)

      

      The number of delete actions performed on a table.

      

      

    Updates -> (long)

      

      The number of update actions performed on a table.

      

      

    Ddls -> (long)

      

      The Data Definition Language (DDL) used to build and modify the structure of your tables.

      

      

    FullLoadRows -> (long)

      

      The number of rows added during the Full Load operation.

      

      

    FullLoadCondtnlChkFailedRows -> (long)

      

      The number of rows that failed conditional checks during the Full Load operation (valid only for DynamoDB as a target migrations).

      

      

    FullLoadErrorRows -> (long)

      

      The number of rows that failed to load during the Full Load operation (valid only for DynamoDB as a target migrations).

      

      

    LastUpdateTime -> (timestamp)

      

      The last time the table was updated.

      

      

    TableState -> (string)

      

      The state of the table.

      

      

    

  

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

