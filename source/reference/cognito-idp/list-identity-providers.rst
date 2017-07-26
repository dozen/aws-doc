[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp list-identity-providers:


***********************
list-identity-providers
***********************



===========
Description
===========



Lists information about all identity providers for a user pool.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/ListIdentityProviders>`_


========
Synopsis
========

::

    list-identity-providers
  --user-pool-id <value>
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID.

  

``--max-results`` (integer)


  The maximum number of identity providers to return.

  

``--next-token`` (string)


  A pagination token.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Providers -> (list)

  

  A list of identity provider objects.

  

  (structure)

    

    A container for identity provider details.

    

    ProviderName -> (string)

      

      The identity provider name.

      

      

    ProviderType -> (string)

      

      The identity provider type.

      

      

    LastModifiedDate -> (timestamp)

      

      The date the provider was last modified.

      

      

    CreationDate -> (timestamp)

      

      The date the provider was added to the user pool.

      

      

    

  

NextToken -> (string)

  

  A pagination token.

  

  

