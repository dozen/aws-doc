[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm create-resource-data-sync:


*************************
create-resource-data-sync
*************************



===========
Description
===========



Creates a resource data sync configuration to a single bucket in Amazon S3. This is an asynchronous operation that returns immediately. After a successful initial sync is completed, the system continuously syncs data to the Amazon S3 bucket. To check the status of the sync, use the `list-resource-data-sync <API_ListResourceDataSync.html>`_ operation.

 

By default, data is not encrypted in Amazon S3. We strongly recommend that you enable encryption in Amazon S3 to ensure secure data storage. We also recommend that you secure access to the Amazon S3 bucket by creating a restrictive bucket policy. To view an example of a restrictive Amazon S3 bucket policy for Resource Data Sync, see `Configuring Resource Data Sync for Inventory <http://docs.aws.amazon.com/systems-manager/latest/userguide/sysman-inventory-configuring.html#sysman-inventory-datasync>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/CreateResourceDataSync>`_


========
Synopsis
========

::

    create-resource-data-sync
  --sync-name <value>
  --s3-destination <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--sync-name`` (string)


  A name for the configuration.

  

``--s3-destination`` (structure)


  Amazon S3 configuration details for the sync.

  



Shorthand Syntax::

    BucketName=string,Prefix=string,SyncFormat=string,Region=string




JSON Syntax::

  {
    "BucketName": "string",
    "Prefix": "string",
    "SyncFormat": "JsonSerDe",
    "Region": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

