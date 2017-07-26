[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline put-job-failure-result:


**********************
put-job-failure-result
**********************



===========
Description
===========



Represents the failure of a job as returned to the pipeline by a job worker. Only used for custom actions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/PutJobFailureResult>`_


========
Synopsis
========

::

    put-job-failure-result
  --job-id <value>
  --failure-details <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-id`` (string)


  The unique system-generated ID of the job that failed. This is the same ID returned from PollForJobs.

  

``--failure-details`` (structure)


  The details about the failure of a job.

  



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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None