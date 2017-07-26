[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline put-third-party-job-success-result:


**********************************
put-third-party-job-success-result
**********************************



===========
Description
===========



Represents the success of a third party job as returned to the pipeline by a job worker. Only used for partner actions.



========
Synopsis
========

::

    put-third-party-job-success-result
  --job-id <value>
  --client-token <value>
  [--current-revision <value>]
  [--continuation-token <value>]
  [--execution-details <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--job-id`` (string)


  The ID of the job that successfully completed. This is the same ID returned from PollForThirdPartyJobs.

  

``--client-token`` (string)


  The clientToken portion of the clientId and clientToken pair used to verify that the calling entity is allowed access to the job and its details.

  

``--current-revision`` (structure)


  Represents information about a current revision.

  



Shorthand Syntax::

    revision=string,changeIdentifier=string




JSON Syntax::

  {
    "revision": "string",
    "changeIdentifier": "string"
  }



``--continuation-token`` (string)


  A system-generated token, such as a AWS CodeDeploy deployment ID, that a job uses in order to continue the job asynchronously.

  

``--execution-details`` (structure)


  The details of the actions taken and results produced on an artifact as it passes through stages in the pipeline.

  



Shorthand Syntax::

    summary=string,externalExecutionId=string,percentComplete=integer




JSON Syntax::

  {
    "summary": "string",
    "externalExecutionId": "string",
    "percentComplete": integer
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None