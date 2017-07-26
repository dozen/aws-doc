[ :ref:`aws <cli:aws>` . :ref:`cognito-sync <cli:aws cognito-sync>` ]

.. _cli:aws cognito-sync describe-identity-usage:


***********************
describe-identity-usage
***********************



===========
Description
===========



Gets usage information for an identity, including number of datasets and data usage.

 

This API can be called with temporary user credentials provided by Cognito Identity or with developer credentials.



========
Synopsis
========

::

    describe-identity-usage
  --identity-pool-id <value>
  --identity-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-pool-id`` (string)
A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

``--identity-id`` (string)
A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

IdentityUsage -> (structure)

  Usage information for the identity.

  IdentityId -> (string)

    A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

    

  IdentityPoolId -> (string)

    A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

    

  LastModifiedDate -> (timestamp)

    Date on which the identity was last modified.

    

  DatasetCount -> (integer)

    Number of datasets for the identity.

    

  DataStorage -> (long)

    Total data storage for this identity.

    

  

