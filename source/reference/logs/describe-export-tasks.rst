[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs describe-export-tasks:


*********************
describe-export-tasks
*********************



===========
Description
===========



Lists the specified export tasks. You can list all your export tasks or filter the results based on task ID or task status.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/DescribeExportTasks>`_


========
Synopsis
========

::

    describe-export-tasks
  [--task-id <value>]
  [--status-code <value>]
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--task-id`` (string)


  The ID of the export task. Specifying a task ID filters the results to zero or one export tasks.

  

``--status-code`` (string)


  The status code of the export task. Specifying a status code filters the results to zero or more export tasks.

  

  Possible values:

  
  *   ``CANCELLED``

  
  *   ``COMPLETED``

  
  *   ``FAILED``

  
  *   ``PENDING``

  
  *   ``PENDING_CANCEL``

  
  *   ``RUNNING``

  

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--limit`` (integer)


  The maximum number of items returned. If you don't specify a value, the default is up to 50 items.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

exportTasks -> (list)

  

  The export tasks.

  

  (structure)

    

    Represents an export task.

    

    taskId -> (string)

      

      The ID of the export task.

      

      

    taskName -> (string)

      

      The name of the export task.

      

      

    logGroupName -> (string)

      

      The name of the log group from which logs data was exported.

      

      

    from -> (long)

      

      The start time, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp prior to this time are not exported.

      

      

    to -> (long)

      

      The end time, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp later than this time are not exported.

      

      

    destination -> (string)

      

      The name of Amazon S3 bucket to which the log data was exported.

      

      

    destinationPrefix -> (string)

      

      The prefix that was used as the start of Amazon S3 key for every object exported.

      

      

    status -> (structure)

      

      The status of the export task.

      

      code -> (string)

        

        The status code of the export task.

        

        

      message -> (string)

        

        The status message related to the status code.

        

        

      

    executionInfo -> (structure)

      

      Execution info about the export task.

      

      creationTime -> (long)

        

        The creation time of the export task, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

        

        

      completionTime -> (long)

        

        The completion time of the export task, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

        

        

      

    

  

nextToken -> (string)

  

  The token for the next set of items to return. The token expires after 24 hours.

  

  

