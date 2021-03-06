[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline report-task-progress:


********************
report-task-progress
********************



===========
Description
===========



Task runners call ``report-task-progress`` when assigned a task to acknowledge that it has the task. If the web service does not receive this acknowledgement within 2 minutes, it assigns the task in a subsequent  poll-for-task call. After this initial acknowledgement, the task runner only needs to report progress every 15 minutes to maintain its ownership of the task. You can change this reporting time from 15 minutes by specifying a ``reportProgressTimeout`` field in your pipeline.

 

If a task runner does not report its status after 5 minutes, AWS Data Pipeline assumes that the task runner is unable to process the task and reassigns the task in a subsequent response to  poll-for-task . Task runners should call ``report-task-progress`` every 60 seconds.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/datapipeline-2012-10-29/ReportTaskProgress>`_


========
Synopsis
========

::

    report-task-progress
  --task-id <value>
  [--fields <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--task-id`` (string)


  The ID of the task assigned to the task runner. This value is provided in the response for  poll-for-task .

  

``--fields`` (list)


  Key-value pairs that define the properties of the ReportTaskProgressInput object.

  



Shorthand Syntax::

    key=string,stringValue=string,refValue=string ...




JSON Syntax::

  [
    {
      "key": "string",
      "stringValue": "string",
      "refValue": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

canceled -> (boolean)

  

  If true, the calling task runner should cancel processing of the task. The task runner does not need to call  set-task-status for canceled tasks.

  

  

