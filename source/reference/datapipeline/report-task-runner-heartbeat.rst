[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline report-task-runner-heartbeat:


****************************
report-task-runner-heartbeat
****************************



===========
Description
===========



Task runners call ``report-task-runner-heartbeat`` every 15 minutes to indicate that they are operational. If the AWS Data Pipeline Task Runner is launched on a resource managed by AWS Data Pipeline, the web service can use this call to detect when the task runner application has failed and restart a new instance.



========
Synopsis
========

::

    report-task-runner-heartbeat
  --taskrunner-id <value>
  [--worker-group <value>]
  [--hostname <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--taskrunner-id`` (string)


  The ID of the task runner. This value should be unique across your AWS account. In the case of AWS Data Pipeline Task Runner launched on a resource managed by AWS Data Pipeline, the web service provides a unique identifier when it launches the application. If you have written a custom task runner, you should assign a unique identifier for the task runner.

  

``--worker-group`` (string)


  The type of task the task runner is configured to accept and process. The worker group is set as a field on objects in the pipeline when they are created. You can only specify a single value for ``workerGroup`` . There are no wildcard values permitted in ``workerGroup`` ; the worker-group must be an exact, case-sensitive, match.

  

``--hostname`` (string)


  The public DNS name of the task runner.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON worker-group provided. The JSON worker-group follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

terminate -> (boolean)

  

  Indicates whether the calling task runner should terminate.

  

  

