[ :ref:`aws <cli:aws>` . :ref:`cognito-sync <cli:aws cognito-sync>` ]

.. _cli:aws cognito-sync list-identity-pool-usage:


************************
list-identity-pool-usage
************************



===========
Description
===========



Gets a list of identity pools registered with Cognito.

 

list-identity-pool-usage can only be called with developer credentials. You cannot make this API call with the temporary user credentials provided by Cognito Identity.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-sync-2014-06-30/ListIdentityPoolUsage>`_


========
Synopsis
========

::

    list-identity-pool-usage
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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

IdentityPoolUsages -> (list)

  Usage information for the identity pools.

  (structure)

    Usage information for the identity pool.

    IdentityPoolId -> (string)

      A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

      

    SyncSessionsCount -> (long)

      Number of sync sessions for the identity pool.

      

    DataStorage -> (long)

      Data storage information for the identity pool.

      

    LastModifiedDate -> (timestamp)

      Date on which the identity pool was last modified.

      

    

  

MaxResults -> (integer)

  The maximum number of results to be returned.

  

Count -> (integer)

  Total number of identities for the identity pool.

  

NextToken -> (string)

  A pagination token for obtaining the next page of results.

  

