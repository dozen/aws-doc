[ :ref:`aws <cli:aws>` . :ref:`sms <cli:aws sms>` ]

.. _cli:aws sms start-on-demand-replication-run:


*******************************
start-on-demand-replication-run
*******************************



===========
Description
===========

The start-on-demand-replication-run API is used to start a ReplicationRun on demand (in addition to those that are scheduled based on your frequency). This ReplicationRun will start immediately. start-on-demand-replication-run is subject to limits on how many on demand ReplicationRuns you may call per 24-hour period.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sms-2016-10-24/StartOnDemandReplicationRun>`_


========
Synopsis
========

::

    start-on-demand-replication-run
  --replication-job-id <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-job-id`` (string)
The unique identifier for a Replication Job.

``--description`` (string)
The description for a Replication Job/Run.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

replicationRunId -> (string)

  The unique identifier for a Replication Run.

  

