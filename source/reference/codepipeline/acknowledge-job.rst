[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline acknowledge-job:


***************
acknowledge-job
***************



===========
Description
===========



Returns information about a specified job and whether that job has been received by the job worker. Only used for custom actions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/AcknowledgeJob>`_


========
Synopsis
========

::

    acknowledge-job
  --job-id <value>
  --nonce <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-id`` (string)


  The unique system-generated ID of the job for which you want to confirm receipt.

  

``--nonce`` (string)


  A system-generated random number that AWS CodePipeline uses to ensure that the job is being worked on by only one job worker. Get this number from the response of the  poll-for-jobs request that returned this job.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

