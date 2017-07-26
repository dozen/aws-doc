[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms modify-replication-task:


***********************
modify-replication-task
***********************



===========
Description
===========



Modifies the specified replication task.

 

You can't modify the task endpoints. The task must be stopped before you can modify it. 

 

For more information about AWS DMS tasks, see the AWS DMS user guide at `Working with Migration Tasks <http://docs.aws.amazon.com/dms/latest/userguide/CHAP_Tasks.html>`_  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/ModifyReplicationTask>`_


========
Synopsis
========

::

    modify-replication-task
  --replication-task-arn <value>
  [--replication-task-identifier <value>]
  [--migration-type <value>]
  [--table-mappings <value>]
  [--replication-task-settings <value>]
  [--cdc-start-time <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-task-arn`` (string)


  The Amazon Resource Name (ARN) of the replication task.

  

``--replication-task-identifier`` (string)


  The replication task identifier.

   

  Constraints:

   

   
  * Must contain from 1 to 255 alphanumeric characters or hyphens. 
   
  * First character must be a letter. 
   
  * Cannot end with a hyphen or contain two consecutive hyphens. 
   

  

``--migration-type`` (string)


  The migration type.

   

  Valid values: full-load | cdc | full-load-and-cdc

  

  Possible values:

  
  *   ``full-load``

  
  *   ``cdc``

  
  *   ``full-load-and-cdc``

  

  

``--table-mappings`` (string)


  When using the AWS CLI or boto3, provide the path of the JSON file that contains the table mappings. Precede the path with "file://". When working with the DMS API, provide the JSON as the parameter value.

   

  For example, --table-mappings file://mappingfile.json

  

``--replication-task-settings`` (string)


  JSON file that contains settings for the task, such as target metadata settings.

  

``--cdc-start-time`` (timestamp)


  The start time for the Change Data Capture (CDC) operation.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ReplicationTask -> (structure)

  

  The replication task that was modified.

  

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

      

      

    

  

