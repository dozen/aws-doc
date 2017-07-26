[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline poll-for-third-party-jobs:


*************************
poll-for-third-party-jobs
*************************



===========
Description
===========



Determines whether there are any third party jobs for a job worker to act on. Only used for partner actions.

 

.. warning::

  

  When this API is called, AWS CodePipeline returns temporary credentials for the Amazon S3 bucket used to store artifacts for the pipeline, if the action requires access to that Amazon S3 bucket for input or output artifacts.

  



========
Synopsis
========

::

    poll-for-third-party-jobs
  --action-type-id <value>
  [--max-batch-size <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--action-type-id`` (structure)


  Represents information about an action type.

  



Shorthand Syntax::

    category=string,owner=string,provider=string,version=string




JSON Syntax::

  {
    "category": "Source"|"Build"|"Deploy"|"Test"|"Invoke",
    "owner": "AWS"|"ThirdParty"|"Custom",
    "provider": "string",
    "version": "string"
  }



``--max-batch-size`` (integer)


  The maximum number of jobs to return in a poll for jobs call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

jobs -> (list)

  

  Information about the jobs to take action on.

  

  (structure)

    

    A response to a poll-for-third-party-jobs request returned by AWS CodePipeline when there is a job to be worked upon by a partner action.

    

    clientId -> (string)

      

      The clientToken portion of the clientId and clientToken pair used to verify that the calling entity is allowed access to the job and its details.

      

      

    jobId -> (string)

      

      The identifier used to identify the job in AWS CodePipeline.

      

      

    

  

