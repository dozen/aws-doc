[ :ref:`aws <cli:aws>` . :ref:`cognito-sync <cli:aws cognito-sync>` ]

.. _cli:aws cognito-sync list-datasets:


*************
list-datasets
*************



===========
Description
===========



Lists datasets for an identity. With Amazon Cognito Sync, each identity has access only to its own data. Thus, the credentials used to make this API call need to have access to the identity data.

 

list-datasets can be called with temporary user credentials provided by Cognito Identity or with developer credentials. You should use the Cognito Identity credentials to make this API call.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-sync-2014-06-30/ListDatasets>`_


========
Synopsis
========

::

    list-datasets
  --identity-pool-id <value>
  --identity-id <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-pool-id`` (string)
A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

``--identity-id`` (string)
A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

``--next-token`` (string)
A pagination token for obtaining the next page of results.

``--max-results`` (integer)
The maximum number of results to be returned.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Datasets -> (list)

  A set of datasets.

  (structure)

    A collection of data for an identity pool. An identity pool can have multiple datasets. A dataset is per identity and can be general or associated with a particular entity in an application (like a saved game). Datasets are automatically created if they don't exist. Data is synced by dataset, and a dataset can hold up to 1MB of key-value pairs.

    IdentityId -> (string)

      A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

      

    DatasetName -> (string)

      A string of up to 128 characters. Allowed characters are a-z, A-Z, 0-9, '_' (underscore), '-' (dash), and '.' (dot).

      

    CreationDate -> (timestamp)

      Date on which the dataset was created.

      

    LastModifiedDate -> (timestamp)

      Date when the dataset was last modified.

      

    LastModifiedBy -> (string)

      The device that made the last change to this dataset.

      

    DataStorage -> (long)

      Total size in bytes of the records in this dataset.

      

    NumRecords -> (long)

      Number of records in this dataset.

      

    

  

Count -> (integer)

  Number of datasets returned.

  

NextToken -> (string)

  A pagination token for obtaining the next page of results.

  

