[ :ref:`aws <cli:aws>` . :ref:`sms <cli:aws sms>` ]

.. _cli:aws sms delete-replication-job:


**********************
delete-replication-job
**********************



===========
Description
===========

The delete-replication-job API is used to delete a ReplicationJob, resulting in no further ReplicationRuns. This will delete the contents of the S3 bucket used to store SMS artifacts, but will not delete any AMIs created by the SMS service.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sms-2016-10-24/DeleteReplicationJob>`_


========
Synopsis
========

::

    delete-replication-job
  --replication-job-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-job-id`` (string)
The unique identifier for a Replication Job.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

