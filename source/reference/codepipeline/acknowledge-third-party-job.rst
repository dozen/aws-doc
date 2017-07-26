[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline acknowledge-third-party-job:


***************************
acknowledge-third-party-job
***************************



===========
Description
===========



Confirms a job worker has received the specified job. Only used for partner actions.



========
Synopsis
========

::

    acknowledge-third-party-job
  --job-id <value>
  --nonce <value>
  --client-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--job-id`` (string)


  The unique system-generated ID of the job.

  

``--nonce`` (string)


  A system-generated random number that AWS CodePipeline uses to ensure that the job is being worked on by only one job worker. This number must be returned in the response.

  

``--client-token`` (string)


  The clientToken portion of the clientId and clientToken pair used to verify that the calling entity is allowed access to the job and its details.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

status -> (string)

  

  The status information for the third party job, if any.

  

  

