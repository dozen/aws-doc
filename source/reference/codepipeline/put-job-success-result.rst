[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline put-job-success-result:


**********************
put-job-success-result
**********************



===========
Description
===========



Represents the success of a job as returned to the pipeline by a job worker. Only used for custom actions.



========
Synopsis
========

::

    put-job-success-result
  --job-id <value>
  [--current-revision <value>]
  [--continuation-token <value>]
  [--execution-details <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--job-id`` (string)


  The unique system-generated ID of the job that succeeded. This is the same ID returned from PollForJobs.

  

``--current-revision`` (structure)


  The ID of the current revision of the artifact successfully worked upon by the job. 

  



Shorthand Syntax::

    revision=string,changeIdentifier=string




JSON Syntax::

  {
    "revision": "string",
    "changeIdentifier": "string"
  }



``--continuation-token`` (string)


  A system-generated token, such as a AWS CodeDeploy deployment ID, that the successful job used to complete a job asynchronously. 

  

``--execution-details`` (structure)


  The execution details of the successful job, such as the actions taken by the job worker. 

  



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