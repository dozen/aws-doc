[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline poll-for-task:


*************
poll-for-task
*************



===========
Description
===========



Task runners call ``poll-for-task`` to receive a task to perform from AWS Data Pipeline. The task runner specifies which tasks it can perform by setting a value for the ``workerGroup`` parameter. The task returned can come from any of the pipelines that match the ``workerGroup`` value passed in by the task runner and that was launched using the IAM user credentials specified by the task runner.

 

If tasks are ready in the work queue, ``poll-for-task`` returns a response immediately. If no tasks are available in the queue, ``poll-for-task`` uses long-polling and holds on to a poll connection for up to a 90 seconds, during which time the first newly scheduled task is handed to the task runner. To accomodate this, set the socket timeout in your task runner to 90 seconds. The task runner should not call ``poll-for-task`` again on the same ``workerGroup`` until it receives a response, and this can take up to 90 seconds. 



========
Synopsis
========

::

    poll-for-task
  --worker-group <value>
  [--hostname <value>]
  [--instance-identity <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--worker-group`` (string)


  The type of task the task runner is configured to accept and process. The worker group is set as a field on objects in the pipeline when they are created. You can only specify a single value for ``workerGroup`` in the call to ``poll-for-task`` . There are no wildcard values permitted in ``workerGroup`` ; the worker-group must be an exact, case-sensitive, match.

  

``--hostname`` (string)


  The public DNS name of the calling task runner.

  

``--instance-identity`` (structure)


  Identity information for the EC2 instance that is hosting the task runner. You can get this value from the instance using ``http://169.254.169.254/latest/meta-data/instance-id`` . For more information, see `Instance Metadata`_ in the *Amazon Elastic Compute Cloud User Guide.* Passing in this value proves that your task runner is running on an EC2 instance, and ensures the proper AWS Data Pipeline service charges are applied to your pipeline.

  



Shorthand Syntax::

    document=string,signature=string




JSON Syntax::

  {
    "document": "string",
    "signature": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON worker-group provided. The JSON worker-group follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

taskObject -> (structure)

  

  The information needed to complete the task that is being assigned to the task runner. One of the fields returned in this object is ``taskId`` , which contains an identifier for the task being assigned. The calling task runner uses ``taskId`` in subsequent calls to  report-task-progress and  set-task-status .

  

  taskId -> (string)

    

    An internal identifier for the task. This ID is passed to the  set-task-status and  report-task-progress actions.

    

    

  pipelineId -> (string)

    

    The ID of the pipeline that provided the task.

    

    

  attemptId -> (string)

    

    The ID of the pipeline task attempt object. AWS Data Pipeline uses this value to track how many times a task is attempted.

    

    

  objects -> (map)

    

    Connection information for the location where the task runner will publish the output of the task.

    

    key -> (string)

      

      

    value -> (structure)

      

      Contains information about a pipeline object. This can be a logical, physical, or physical attempt pipeline object. The complete set of components of a pipeline defines the pipeline.

      

      id -> (string)

        

        The ID of the object.

        

        

      name -> (string)

        

        The name of the object.

        

        

      fields -> (list)

        

        Key-value pairs that define the properties of the object.

        

        (structure)

          

          A key-value pair that describes a property of a pipeline object. The value is specified as either a worker-group value (``StringValue`` ) or a reference to another object (``RefValue`` ) but not as both.

          

          key -> (string)

            

            The field identifier.

            

            

          stringValue -> (string)

            

            The field value, expressed as a String.

            

            

          refValue -> (string)

            

            The field value, expressed as the identifier of another object.

            

            

          

        

      

    

  



.. _Instance Metadata: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AESDG-chapter-instancedata.html
