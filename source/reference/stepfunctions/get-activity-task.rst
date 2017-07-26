[ :ref:`aws <cli:aws>` . :ref:`stepfunctions <cli:aws stepfunctions>` ]

.. _cli:aws stepfunctions get-activity-task:


*****************
get-activity-task
*****************



===========
Description
===========



Used by workers to retrieve a task (with the specified activity ARN) scheduled for execution by a running state machine. This initiates a long poll, where the service holds the HTTP connection open and responds as soon as a task becomes available (i.e. an execution of a task of this type is needed.) The maximum time the service holds on to the request before responding is 60 seconds. If no task is available within 60 seconds, the poll will return an empty result, that is, the ``taskToken`` returned is an empty string.

 

.. warning::

   

  Workers should set their client side socket timeout to at least 65 seconds (5 seconds higher than the maximum time the service may hold the poll request).

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/states-2016-11-23/GetActivityTask>`_


========
Synopsis
========

::

    get-activity-task
  --activity-arn <value>
  [--worker-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--activity-arn`` (string)


  The Amazon Resource worker-name (ARN) of the activity to retrieve tasks from.

  

``--worker-name`` (string)


  An arbitrary name may be provided in order to identify the worker that the task is assigned to. This name will be used when it is logged in the execution history.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

taskToken -> (string)

  

  A token that identifies the scheduled task. This token must be copied and included in subsequent calls to  send-task-heartbeat ,  send-task-success or  send-task-failure in order to report the progress or completion of the task.

  

  

input -> (string)

  

  The JSON input data for the task.

  

  

