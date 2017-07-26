[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs create-export-task:


******************
create-export-task
******************



===========
Description
===========



Creates an export task, which allows you to efficiently export data from a log group to an Amazon S3 bucket.

 

This is an asynchronous call. If all the required information is provided, this operation initiates an export task and responds with the ID of the task. After the task has started, you can use  describe-export-tasks to get the status of the export task. Each account can only have one active (``RUNNING`` or ``PENDING`` ) export task at a time. To cancel an export task, use  cancel-export-task .

 

You can export logs from multiple log groups or multiple time ranges to the same S3 bucket. To separate out log data for each export task, you can specify a prefix that will be used as the Amazon S3 key prefix for all exported objects.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/CreateExportTask>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--task-name`` (string)


  The name of the export task.

  

``--log-group-name`` (string)


  The name of the log group.

  

``--log-stream-name-prefix`` (string)


  Export only log streams that match the provided prefix. If you don't specify a value, no prefix filter is applied.

  

``--from`` (long)


  The start time of the range for the request, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp earlier than this time are not exported.

  

``--to`` (long)


  The end time of the range for the request, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp later than this time are not exported.

  

``--destination`` (string)


  The name of S3 bucket for the exported log data. The bucket must be in the same AWS region.

  

``--destination-prefix`` (string)


  The prefix used as the start of the key for every object exported. If you don't specify a value, the default is ``exportedlogs`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

taskId -> (string)

  

  The ID of the export task.

  

  

