[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline put-action-revision:


*******************
put-action-revision
*******************



===========
Description
===========



Provides information to AWS CodePipeline about new revisions to a source.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/PutActionRevision>`_


========
Synopsis
========

::

    put-action-revision
  --pipeline-name <value>
  --stage-name <value>
  --action-name <value>
  --action-revision <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-name`` (string)


  The name of the pipeline that will start processing the revision to the source.

  

``--stage-name`` (string)


  The name of the stage that contains the action that will act upon the revision.

  

``--action-name`` (string)


  The name of the action that will process the revision.

  

``--action-revision`` (structure)


  Represents information about the version (or revision) of an action.

  



Shorthand Syntax::

    revisionId=string,revisionChangeId=string,created=timestamp




JSON Syntax::

  {
    "revisionId": "string",
    "revisionChangeId": "string",
    "created": timestamp
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

newRevision -> (boolean)

  

  Indicates whether the artifact revision was previously used in an execution of the specified pipeline.

  

  

pipelineExecutionId -> (string)

  

  The ID of the current workflow state of the pipeline.

  

  

