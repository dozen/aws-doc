[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms create-replication-task:


***********************
create-replication-task
***********************



===========
Description
===========



Creates a replication task using the specified parameters.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/CreateReplicationTask>`_


========
Synopsis
========

::

    create-replication-task
  --replication-task-identifier <value>
  --source-endpoint-arn <value>
  --target-endpoint-arn <value>
  --replication-instance-arn <value>
  --migration-type <value>
  --table-mappings <value>
  [--replication-task-settings <value>]
  [--cdc-start-time <value>]
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-task-identifier`` (string)


  The replication task identifier.

   

  Constraints:

   

   
  * Must contain from 1 to 255 alphanumeric characters or hyphens. 
   
  * First character must be a letter. 
   
  * Cannot end with a hyphen or contain two consecutive hyphens. 
   

  

``--source-endpoint-arn`` (string)


  The Amazon Resource Name (ARN) string that uniquely identifies the endpoint.

  

``--target-endpoint-arn`` (string)


  The Amazon Resource Name (ARN) string that uniquely identifies the endpoint.

  

``--replication-instance-arn`` (string)


  The Amazon Resource Name (ARN) of the replication instance.

  

``--migration-type`` (string)


  The migration type.

  

  Possible values:

  
  *   ``full-load``

  
  *   ``cdc``

  
  *   ``full-load-and-cdc``

  

  

``--table-mappings`` (string)


  When using the AWS CLI or boto3, provide the path of the JSON file that contains the table mappings. Precede the path with "file://". When working with the DMS API, provide the JSON as the parameter value.

   

  For example, --table-mappings file://mappingfile.json

  

``--replication-task-settings`` (string)


  Settings for the task, such as target metadata settings. For a complete list of task settings, see `Task Settings for AWS Database Migration Service Tasks <http://docs.aws.amazon.com/dms/latest/userguide/CHAP_Tasks.CustomizingTasks.TaskSettings.html>`_ .

  

``--cdc-start-time`` (timestamp)


  The start time for the Change Data Capture (CDC) operation.

  

``--tags`` (list)


  Tags to be added to the replication instance.

  



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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command creates a replication task to copy data from one DB instance behind a DMS endpoint to another using a replication instance::

  aws dms create-replication-task --replicationtask-identifier my-replication-task --target-endpoint-arn arn:aws:dms:us-east-1:123456789012:endpoint:HTWNT57CLN2WGVBUJQXJZASXWE --source-endpoint-arn arn:aws:dms:us-east-1:123456789012:endpoint:ZW5UAN6P4E77EC7YWHK4RZZ3BE --replication-instance-arn arn:aws:dms:us-east-1:123456789012:rep:6UTDJGBOUS3VI3SUWA66XFJCJQ --migration-type full-load --table-mappings 'file://table-mappings.json'

The file ``table-mappings.json`` is a JSON document in the current folder that specifies table mappings::

  {
    "TableMappings": [
      {
        "Type": "Include",
        "SourceSchema": "company",
        "SourceTable": "emp%"
      },
      {
        "Type": "Include",
        "SourceSchema": "employees",
        "SourceTable": "%"
      },
      {
        "Type": "Exclude",
        "SourceSchema": "source101",
        "SourceTable": "dep%"
      },
      {
        "Type": "Exclude",
        "SourceSchema": "source102",
        "SourceTable": "%"
      },
      {
        "Type": "Explicit",
        "SourceSchema": "company",
        "SourceTable": "managers"
      },
      {
        "Type": "Explicit",
        "SourceSchema": "company",
        "SourceTable": "locations"
      }
      ]
  }


Output::

  {
    "ReplicationTask": {
      "SourceEndpointArn": "arn:aws:dms:us-east-1:123456789012:endpoint:ZW5UAN6P4E77EC7YWHK4RZZ3BE",
      "ReplicationTaskIdentifier": "task1",
      "ReplicationInstanceArn": "arn:aws:dms:us-east-1:123456789012:rep:6UTDJGBOUS3VI3SUWA66XFJCJQ",
      "TableMappings": "{\n \"TableMappings\": [\n {\n \"Type\":\"Include\",\n \"SourceSchema\": \"/\",\n \"SourceTable\": \"/\"\n}\n ]\n}\n\n",
      "Status": "creating",
      "ReplicationTaskArn": "arn:aws:dms:us-east-1:123456789012:task:OEAMB3NXSTZ6LFYZFEPPBBXPYM",
      "ReplicationTaskCreationDate": 1457658407.492,
      "MigrationType": "full-load",
      "TargetEndpointArn": "arn:aws:dms:us-east-1:123456789012:endpoint:ASXWXJZLNWNT5HTWCGV2BUJQ7E",
      "ReplicationTaskSettings": "{\"TargetMetadata\":{\"TargetSchema\":\"\",\"SupportLobs\":true,\"FullLobMode\":true,\"LobChunkSize\":64,\"LimitedSizeLobMode\":false,\"LobMaxSize\":0},\"FullLoadSettings\":{\"FullLoadEnabled\":true,\"ApplyChangesEnabled\":false,\"TargetTablePrepMode\":\"DROP_AND_CREATE\",\"CreatePkAfterFullLoad\":false,\"StopTaskCachedChangesApplied\":false,\"StopTaskCachedChangesNotApplied\":false,\"ResumeEnabled\":false,\"ResumeMinTableSize\":100000,\"ResumeOnlyClusteredPKTables\":true,\"MaxFullLoadSubTasks\":8,\"TransactionConsistencyTimeout\":600,\"CommitRate\":10000},\"Logging\":{\"EnableLogging\":false}}"
    }
  }


======
Output
======

ReplicationTask -> (structure)

  

  The replication task that was created.

  

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

      

      

    

  

