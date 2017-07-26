[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs create-export-task:


******************
create-export-task
******************



===========
Description
===========



Creates an ``ExportTask`` which allows you to efficiently export data from a Log Group to your Amazon S3 bucket. 

 

This is an asynchronous call. If all the required information is provided, this API will initiate an export task and respond with the task Id. Once started, ``describe-export-tasks`` can be used to get the status of an export task. You can only have one active (``RUNNING`` or ``PENDING`` ) export task at a time, per account. 

 

You can export logs from multiple log groups or multiple time ranges to the same Amazon S3 bucket. To separate out log data for each export task, you can specify a prefix that will be used as the Amazon S3 key prefix for all exported objects. 



========
Synopsis
========

::

    create-export-task
  [--task-name <value>]
  --log-group-name <value>
  [--log-stream-name-prefix <value>]
  --from <value>
  --to <value>
  --destination <value>
  [--destination-prefix <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--task-name`` (string)


  The name of the export task.

  

``--log-group-name`` (string)


  The name of the log group to export.

  

``--log-stream-name-prefix`` (string)


  Will only export log streams that match the provided logStreamNamePrefix. If you don't specify a value, no prefix filter is applied.

  

``--from`` (long)


  A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. It indicates the start time of the range for the request. Events with a timestamp prior to this time will not be exported.

  

``--to`` (long)


  A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. It indicates the end time of the range for the request. Events with a timestamp later than this time will not be exported.

  

``--destination`` (string)


  Name of Amazon S3 bucket to which the log data will be exported.

   

  **Note:** Only buckets in the same AWS region are supported.

  

``--destination-prefix`` (string)


  Prefix that will be used as the start of Amazon S3 key for every object exported. If not specified, this defaults to 'exportedlogs'.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

taskId -> (string)

  

  Id of the export task that got created.

  

  

