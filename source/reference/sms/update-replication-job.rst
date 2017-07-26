[ :ref:`aws <cli:aws>` . :ref:`sms <cli:aws sms>` ]

.. _cli:aws sms update-replication-job:


**********************
update-replication-job
**********************



===========
Description
===========

The update-replication-job API is used to change the settings of your existing ReplicationJob created using CreateReplicationJob. Calling this API will affect the next scheduled ReplicationRun.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sms-2016-10-24/UpdateReplicationJob>`_


========
Synopsis
========

::

    update-replication-job
  --replication-job-id <value>
  [--frequency <value>]
  [--next-replication-run-start-time <value>]
  [--license-type <value>]
  [--role-name <value>]
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-job-id`` (string)
The unique identifier for a Replication Job.

``--frequency`` (integer)
Interval between Replication Runs. This value is specified in hours, and represents the time between consecutive Replication Runs.

``--next-replication-run-start-time`` (timestamp)
next-replication-run-start-time of an operation

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

