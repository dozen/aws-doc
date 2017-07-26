[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms describe-replication-tasks:


**************************
describe-replication-tasks
**************************



===========
Description
===========



Returns information about replication tasks for your account in the current region.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/DescribeReplicationTasks>`_


========
Synopsis
========

::

    describe-replication-tasks
  [--filters <value>]
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  Filters applied to the describe action.

   

  Valid filter names: replication-task-arn | replication-task-id | migration-type | endpoint-arn | replication-instance-arn

  



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


  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

ReplicationTasks -> (list)

  

  A description of the replication tasks.

  

  (structure)

    

    

    

    ReplicationTaskIdentifier -> (string)

      

      The replication task identifier.

       

      Constraints:

       

       
      * Must contain from 1 to 255 alphanumeric characters or hyphens. 
       
      * First character must be a letter. 
       
      * Cannot end with a hyphen or contain two consecutive hyphens. 
       

      

      

    SourceEndpointArn -> (string)

      

      The Amazon Resource Name (ARN) string that uniquely identifies the endpoint.

      

      

    TargetEndpointArn -> (string)

      

      The Amazon Resource Name (ARN) string that uniquely identifies the endpoint.

      

      

    ReplicationInstanceArn -> (string)

      

      The Amazon Resource Name (ARN) of the replication instance.

      

      

    MigrationType -> (string)

      

      The type of migration.

      

      

    TableMappings -> (string)

      

      Table mappings specified in the task.

      

      

    ReplicationTaskSettings -> (string)

      

      The settings for the replication task.

      

      

    Status -> (string)

      

      The status of the replication task.

      

      

    LastFailureMessage -> (string)

      

      The last error (failure) message generated for the replication instance.

      

      

    StopReason -> (string)

      

      The reason the replication task was stopped.

      

      

    ReplicationTaskCreationDate -> (timestamp)

      

      The date the replication task was created.

      

      

    ReplicationTaskStartDate -> (timestamp)

      

      The date the replication task is scheduled to start.

      

      

    ReplicationTaskArn -> (string)

      

      The Amazon Resource Name (ARN) of the replication task.

      

      

    ReplicationTaskStats -> (structure)

      

      The statistics for the task, including elapsed time, tables loaded, and table errors.

      

      FullLoadProgressPercent -> (integer)

        

        The percent complete for the full load migration task.

        

        

      ElapsedTimeMillis -> (long)

        

        The elapsed time of the task, in milliseconds.

        

        

      TablesLoaded -> (integer)

        

        The number of tables loaded for this task.

        

        

      TablesLoading -> (integer)

        

        The number of tables currently loading for this task.

        

        

      TablesQueued -> (integer)

        

        The number of tables queued for this task.

        

        

      TablesErrored -> (integer)

        

        The number of errors that have occurred during this task.

        

        

      

    

  

