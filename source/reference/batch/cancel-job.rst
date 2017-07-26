[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch cancel-job:


**********
cancel-job
**********



===========
Description
===========



Cancels jobs in an AWS Batch job queue. Jobs that are in the ``SUBMITTED`` , ``PENDING`` , or ``RUNNABLE`` state are cancelled. Jobs that have progressed to ``STARTING`` or ``RUNNING`` are not cancelled (but the API operation still succeeds, even if no jobs are cancelled); these jobs must be terminated with the  terminate-job operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/CancelJob>`_


========
Synopsis
========

::

    cancel-job
  --job-id <value>
  --reason <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-id`` (string)


  A list of up to 100 job IDs to cancel.

  

``--reason`` (string)


  A message to attach to the job that explains the reason for cancelling it. This message is returned by future  describe-jobs operations on the job. This message is also recorded in the AWS Batch activity logs. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To cancel a job**

This example cancels a job with the specified job ID.

Command::

  aws batch cancel-job --job-id bcf0b186-a532-4122-842e-2ccab8d54efb --reason "Cancelling job."


======
Output
======

