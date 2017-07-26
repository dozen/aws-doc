[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline acknowledge-third-party-job:


***************************
acknowledge-third-party-job
***************************



===========
Description
===========



Confirms a job worker has received the specified job. Only used for partner actions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/AcknowledgeThirdPartyJob>`_


========
Synopsis
========

::

    acknowledge-third-party-job
  --job-id <value>
  --nonce <value>
  --client-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-id`` (string)


  The unique system-generated ID of the job.

  

``--nonce`` (string)


  A system-generated random number that AWS CodePipeline uses to ensure that the job is being worked on by only one job worker. Get this number from the response to a  get-third-party-job-details request.

  

``--client-token`` (string)


  The clientToken portion of the clientId and clientToken pair used to verify that the calling entity is allowed access to the job and its details.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

status -> (string)

  

  The status information for the third party job, if any.

  

  

