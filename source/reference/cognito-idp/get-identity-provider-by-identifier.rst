[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp get-identity-provider-by-identifier:


***********************************
get-identity-provider-by-identifier
***********************************



===========
Description
===========



Gets the specified identity provider.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/GetIdentityProviderByIdentifier>`_


========
Synopsis
========

::

    get-identity-provider-by-identifier
  --user-pool-id <value>
  --idp-identifier <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID.

  

``--idp-identifier`` (string)


  The identity provider ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IdentityProvider -> (structure)

  

  The identity provider object.

  

  UserPoolId -> (string)

    

    The user pool ID.

    

    

  ProviderName -> (string)

    

    The identity provider name.

    

    

  ProviderType -> (string)

    

    The identity provider type.

    

    

  ProviderDetails -> (map)

    

    The identity provider details, such as ``MetadataURL`` and ``MetadataFile`` .

    

    key -> (string)

      

      

    value -> (string)

      

      

    

  AttributeMapping -> (map)

    

    A mapping of identity provider attributes to standard and custom user pool attributes.

    

    key -> (string)

      

      

    value -> (string)

      

      

    

  IdpIdentifiers -> (list)

    

    A list of identity provider identifiers.

    

    (string)

      

      

    

  LastModifiedDate -> (timestamp)

    

    The date the identity provider was last modified.

    

    

  CreationDate -> (timestamp)

    

    The date the identity provider was created.

    

    

  

