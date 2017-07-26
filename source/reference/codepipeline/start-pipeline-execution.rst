[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline start-pipeline-execution:


************************
start-pipeline-execution
************************



===========
Description
===========



Starts the specified pipeline. Specifically, it begins processing the latest commit to the source location specified as part of the pipeline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/StartPipelineExecution>`_


========
Synopsis
========

::

    start-pipeline-execution
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the pipeline to start.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To run the latest revision through a pipeline**

This example runs the latest revision present in the source stage of a pipeline through the pipeline named "MyFirstPipeline".

Command::

  aws codepipeline start-pipeline-execution --name MyFirstPipeline


Output::

  {
    "pipelineExecutionId": "3137f7cb-7cf7-EXAMPLE"
  }

======
Output
======

pipelineExecutionId -> (string)

  

  The unique system-generated ID of the pipeline execution that was started.

  

  

