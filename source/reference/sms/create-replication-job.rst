[ :ref:`aws <cli:aws>` . :ref:`sms <cli:aws sms>` ]

.. _cli:aws sms create-replication-job:


**********************
create-replication-job
**********************



===========
Description
===========

The create-replication-job API is used to create a ReplicationJob to replicate a server on AWS. Call this API to first create a ReplicationJob, which will then schedule periodic ReplicationRuns to replicate your server to AWS. Each ReplicationRun will result in the creation of an AWS AMI.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sms-2016-10-24/CreateReplicationJob>`_


========
Synopsis
========

::

    create-replication-job
  --server-id <value>
  --seed-replication-time <value>
  --frequency <value>
  [--license-type <value>]
  [--role-name <value>]
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--server-id`` (string)
Unique Identifier for a server

``--seed-replication-time`` (timestamp)
seed-replication-time of an operation

``--frequency`` (integer)
Interval between Replication Runs. This value is specified in hours, and represents the time between consecutive Replication Runs.

``--license-type`` (string)
The license type to be used for the Amazon Machine Image (AMI) created after a successful ReplicationRun.

  Possible values:

  
  *   ``AWS``

  
  *   ``BYOL``

  

  

``--role-name`` (string)
Name of service role in customer's account to be used by SMS service.

``--description`` (string)
The description for a Replication Job/Run.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

replicationJobId -> (string)

  The unique identifier for a Replication Job.

  

