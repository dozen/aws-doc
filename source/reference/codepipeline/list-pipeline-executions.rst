[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline list-pipeline-executions:


************************
list-pipeline-executions
************************



===========
Description
===========



Gets a summary of the most recent executions for a pipeline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/ListPipelineExecutions>`_


========
Synopsis
========

::

    list-pipeline-executions
  --pipeline-name <value>
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-name`` (string)


  The name of the pipeline for which you want to get execution summary information.

  

``--max-results`` (integer)


  The maximum number of results to return in a single call. To retrieve the remaining results, make another call with the returned nextToken value. The available pipeline execution history is limited to the most recent 12 months, based on pipeline execution start times. Default value is 100.

  

``--next-token`` (string)


  The token that was returned from the previous list pipeline executions call, which can be used to return the next set of pipeline executions in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

pipelineExecutionSummaries -> (list)

  

  A list of executions in the history of a pipeline.

  

  (structure)

    

    Summary information about a pipeline execution.

    

    pipelineExecutionId -> (string)

      

      The ID of the pipeline execution.

      

      

    status -> (string)

      

      The status of the pipeline execution.

       

       
      * InProgress: The pipeline execution is currently running. 
       
      * Succeeded: The pipeline execution completed successfully.  
       
      * Superseded: While this pipeline execution was waiting for the next stage to be completed, a newer pipeline execution caught up and continued through the pipeline instead.  
       
      * Failed: The pipeline execution did not complete successfully. 
       

      

      

    startTime -> (timestamp)

      

      The date and time when the pipeline execution began, in timestamp format.

      

      

    lastUpdateTime -> (timestamp)

      

      The date and time of the last change to the pipeline execution, in timestamp format.

      

      

    

  

nextToken -> (string)

  

  A token that can be used in the next list pipeline executions call to return the next set of pipeline executions. To view all items in the list, continue to call this operation with each subsequent token until no more nextToken values are returned.

  

  

