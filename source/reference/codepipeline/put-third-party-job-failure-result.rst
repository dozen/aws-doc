[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline put-third-party-job-failure-result:


**********************************
put-third-party-job-failure-result
**********************************



===========
Description
===========



Represents the failure of a third party job as returned to the pipeline by a job worker. Only used for partner actions.



========
Synopsis
========

::

    put-third-party-job-failure-result
  --job-id <value>
  --client-token <value>
  --failure-details <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--job-id`` (string)


  The ID of the job that failed. This is the same ID returned from PollForThirdPartyJobs.

  

``--client-token`` (string)


  The clientToken portion of the clientId and clientToken pair used to verify that the calling entity is allowed access to the job and its details.

  

``--failure-details`` (structure)


  Represents information about failure details.

  



Shorthand Syntax::

    type=string,message=string,externalExecutionId=string




JSON Syntax::

  {
    "type": "JobFailed"|"ConfigurationError"|"PermissionError"|"RevisionOutOfSync"|"RevisionUnavailable"|"SystemUnavailable",
    "message": "string",
    "externalExecutionId": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None