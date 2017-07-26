[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm delete-resource-data-sync:


*************************
delete-resource-data-sync
*************************



===========
Description
===========



Deletes a Resource Data Sync configuration. After the configuration is deleted, changes to inventory data on managed instances are no longer synced with the target Amazon S3 bucket. Deleting a sync configuration does not delete data in the target Amazon S3 bucket.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DeleteResourceDataSync>`_


========
Synopsis
========

::

    delete-resource-data-sync
  --sync-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--sync-name`` (string)


  The name of the configuration to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

