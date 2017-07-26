[ :ref:`aws <cli:aws>` . :ref:`cognito-sync <cli:aws cognito-sync>` ]

.. _cli:aws cognito-sync list-records:


************
list-records
************



===========
Description
===========



Gets paginated records, optionally changed after a particular sync count for a dataset and identity. With Amazon Cognito Sync, each identity has access only to its own data. Thus, the credentials used to make this API call need to have access to the identity data.

 

list-records can be called with temporary user credentials provided by Cognito Identity or with developer credentials. You should use Cognito Identity credentials to make this API call.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-sync-2014-06-30/ListRecords>`_


========
Synopsis
========

::

    list-records
  --identity-pool-id <value>
  --identity-id <value>
  --dataset-name <value>
  [--last-sync-count <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--sync-session-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-pool-id`` (string)
A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

``--identity-id`` (string)
A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

``--dataset-name`` (string)
A string of up to 128 characters. Allowed characters are a-z, A-Z, 0-9, '_' (underscore), '-' (dash), and '.' (dot).

``--last-sync-count`` (long)
The last server sync count for this record.

``--next-token`` (string)
A pagination token for obtaining the next page of results.

``--max-results`` (integer)
The maximum number of results to be returned.

``--sync-session-token`` (string)
A token containing a session ID, identity ID, and expiration.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Records -> (list)

  A list of all records.

  (structure)

    The basic data structure of a dataset.

    Key -> (string)

      The key for the record.

      

    Value -> (string)

      The value for the record.

      

    SyncCount -> (long)

      The server sync count for this record.

      

    LastModifiedDate -> (timestamp)

      The date on which the record was last modified.

      

    LastModifiedBy -> (string)

      The user/device that made the last change to this record.

      

    DeviceLastModifiedDate -> (timestamp)

      The last modified date of the client device.

      

    

  

NextToken -> (string)

  A pagination token for obtaining the next page of results.

  

Count -> (integer)

  Total number of records.

  

DatasetSyncCount -> (long)

  Server sync count for this dataset.

  

LastModifiedBy -> (string)

  The user/device that made the last change to this record.

  

MergedDatasetNames -> (list)

  Names of merged datasets.

  (string)

    

    

  

DatasetExists -> (boolean)

  Indicates whether the dataset exists.

  

DatasetDeletedAfterRequestedSyncCount -> (boolean)

  A boolean value specifying whether to delete the dataset locally.

  

SyncSessionToken -> (string)

  A token containing a session ID, identity ID, and expiration.

  

