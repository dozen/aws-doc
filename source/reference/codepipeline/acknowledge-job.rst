[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline acknowledge-job:


***************
acknowledge-job
***************



===========
Description
===========



Returns information about a specified job and whether that job has been received by the job worker. Only used for custom actions.



========
Synopsis
========

::

    acknowledge-job
  --job-id <value>
  --nonce <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--job-id`` (string)


  The unique system-generated ID of the job for which you want to confirm receipt.

  

``--nonce`` (string)


  A system-generated random number that AWS CodePipeline uses to ensure that the job is being worked on by only one job worker. This number must be returned in the response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To retrieve information about a specified job**

This example returns information about a specified job, including the status of that job if it exists. This is only used for job workers and custom actions. To determine the value of nonce and the job ID, use aws codepipeline poll-for-jobs.

Command::

  aws codecommit acknowledge-job --job-id f4f4ff82-2d11-EXAMPLE --nonce 3

Output::

  {
    "status": "InProgress"
  }

======
Output
======

status -> (string)

  

  Whether the job worker has received the specified job.

  

  

