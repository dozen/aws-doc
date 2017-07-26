[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch terminate-job:


*************
terminate-job
*************



===========
Description
===========



Terminates jobs in a job queue. Jobs that are in the ``STARTING`` or ``RUNNING`` state are terminated, which causes them to transition to ``FAILED`` . Jobs that have not progressed to the ``STARTING`` state are cancelled.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/TerminateJob>`_


========
Synopsis
========

::

    terminate-job
  --job-id <value>
  --reason <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-id`` (string)


  Job IDs to be terminated. Up to 100 jobs can be specified.

  

``--reason`` (string)


  A message to attach to the job that explains the reason for cancelling it. This message is returned by future  describe-jobs operations on the job. This message is also recorded in the AWS Batch activity logs. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To terminate a job**

This example terminates a job with the specified job ID.

Command::

  aws batch terminate-job --job-id 61e743ed-35e4-48da-b2de-5c8333821c84 --reason "Terminating job."


======
Output
======

