[ :ref:`aws <cli:aws>` . :ref:`cognito-sync <cli:aws cognito-sync>` ]

.. _cli:aws cognito-sync describe-identity-pool-usage:


****************************
describe-identity-pool-usage
****************************



===========
Description
===========



Gets usage details (for example, data storage) about a particular identity pool.

 

This API can only be called with developer credentials. You cannot call this API with the temporary user credentials provided by Cognito Identity.



========
Synopsis
========

::

    describe-identity-pool-usage
  --identity-pool-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-pool-id`` (string)
A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

IdentityPoolUsage -> (structure)

  Information about the usage of the identity pool.

  IdentityPoolId -> (string)

    A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

    

  SyncSessionsCount -> (long)

    Number of sync sessions for the identity pool.

    

  DataStorage -> (long)

    Data storage information for the identity pool.

    

  LastModifiedDate -> (timestamp)

    Date on which the identity pool was last modified.

    

  

