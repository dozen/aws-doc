[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline put-action-revision:


*******************
put-action-revision
*******************



===========
Description
===========



Provides information to AWS CodePipeline about new revisions to a source.



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
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

newRevision -> (boolean)

  

  The new revision number or ID for the revision after the action completes.

  

  

pipelineExecutionId -> (string)

  

  The ID of the current workflow state of the pipeline. 

  

  

