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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-sync-2014-06-30/DescribeIdentityPoolUsage>`_


========
Synopsis
========

::

    describe-identity-pool-usage
  --identity-pool-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-pool-id`` (string)
A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

  

