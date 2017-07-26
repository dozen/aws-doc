[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline retry-stage-execution:


*********************
retry-stage-execution
*********************



===========
Description
===========



Resumes the pipeline execution by retrying the last failed actions in a stage.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/RetryStageExecution>`_


========
Synopsis
========

::

    retry-stage-execution
  --pipeline-name <value>
  --stage-name <value>
  --pipeline-execution-id <value>
  --retry-mode <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-name`` (string)


  The name of the pipeline that contains the failed stage.

  

``--stage-name`` (string)


  The name of the failed stage to be retried.

  

``--pipeline-execution-id`` (string)


  The ID of the pipeline execution in the failed stage to be retried. Use the  get-pipeline-state action to retrieve the current pipelineExecutionId of the failed stage

  

``--retry-mode`` (string)


  The scope of the retry attempt. Currently, the only supported value is FAILED_ACTIONS.

  

  Possible values:

  
  *   ``FAILED_ACTIONS``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

pipelineExecutionId -> (string)

  

  The ID of the current workflow execution in the failed stage.

  

  

