[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs describe-export-tasks:


*********************
describe-export-tasks
*********************



===========
Description
===========



Returns all the export tasks that are associated with the AWS account making the request. The export tasks can be filtered based on ``TaskId`` or ``TaskStatus`` . 

 

By default, this operation returns up to 50 export tasks that satisfy the specified filters. If there are more export tasks to list, the response would contain a ``nextToken`` value in the response body. You can also limit the number of export tasks returned in the response by specifying the ``limit`` parameter in the request. 



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
  [--generate-cli-skeleton]




=======
Options
=======

``--task-id`` (string)


  Export task that matches the specified task Id will be returned. This can result in zero or one export task.

  

``--status-code`` (string)


  All export tasks that matches the specified status code will be returned. This can return zero or more export tasks.

  

  Possible values:

  
  *   ``CANCELLED``

  
  *   ``COMPLETED``

  
  *   ``FAILED``

  
  *   ``PENDING``

  
  *   ``PENDING_CANCEL``

  
  *   ``RUNNING``

  

  

``--next-token`` (string)


  A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous ``describe-export-tasks`` request. 

  

``--limit`` (integer)


  The maximum number of items returned in the response. If you don't specify a value, the request would return up to 50 items. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

exportTasks -> (list)

  

  A list of export tasks.

  

  (structure)

    

    Represents an export task.

    

    taskId -> (string)

      

      Id of the export task.

      

      

    taskName -> (string)

      

      The name of the export task.

      

      

    logGroupName -> (string)

      

      The name of the log group from which logs data was exported.

      

      

    from -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp prior to this time are not exported.

      

      

    to -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp later than this time are not exported.

      

      

    destination -> (string)

      

      Name of Amazon S3 bucket to which the log data was exported.

      

      

    destinationPrefix -> (string)

      

      Prefix that was used as the start of Amazon S3 key for every object exported.

      

      

    status -> (structure)

      

      Status of the export task.

      

      code -> (string)

        

        Status code of the export task.

        

        

      message -> (string)

        

        Status message related to the ``code`` .

        

        

      

    executionInfo -> (structure)

      

      Execution info about the export task.

      

      creationTime -> (long)

        

        A point in time when the export task got created.

        

        

      completionTime -> (long)

        

        A point in time when the export task got completed.

        

        

      

    

  

nextToken -> (string)

  

  A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

  

  

