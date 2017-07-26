[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline set-task-status:


***************
set-task-status
***************



===========
Description
===========



Task runners call ``set-task-status`` to notify AWS Data Pipeline that a task is completed and provide information about the final status. A task runner makes this call regardless of whether the task was sucessful. A task runner does not need to call ``set-task-status`` for tasks that are canceled by the web service during a call to  report-task-progress .



========
Synopsis
========

::

    set-task-status
  --task-id <value>
  --task-status <value>
  [--error-id <value>]
  [--error-message <value>]
  [--error-stack-trace <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--task-id`` (string)


  The ID of the task assigned to the task runner. This value is provided in the response for  poll-for-task .

  

``--task-status`` (string)


  If ``FINISHED`` , the task successfully completed. If ``FAILED`` , the task ended unsuccessfully. Preconditions use false.

  

  Possible values:

  
  *   ``FINISHED``

  
  *   ``FAILED``

  
  *   ``FALSE``

  

  

``--error-id`` (string)


  If an error occurred during the task, this value specifies the error code. This value is set on the physical attempt object. It is used to display error information to the user. It should not start with error-stack-trace "Service_" which is reserved by the system.

  

``--error-message`` (string)


  If an error occurred during the task, this value specifies a text description of the error. This value is set on the physical attempt object. It is used to display error information to the user. The web service does not parse this value.

  

``--error-stack-trace`` (string)


  If an error occurred during the task, this value specifies the stack trace associated with the error. This value is set on the physical attempt object. It is used to display error information to the user. The web service does not parse this value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON error-stack-trace provided. The JSON error-stack-trace follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

