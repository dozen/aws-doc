[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp create-identity-provider:


************************
create-identity-provider
************************



===========
Description
===========



Creates an identity provider for a user pool.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/CreateIdentityProvider>`_


========
Synopsis
========

::

    create-identity-provider
  --user-pool-id <value>
  --provider-name <value>
  --provider-type <value>
  --provider-details <value>
  [--attribute-mapping <value>]
  [--idp-identifiers <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID.

  

``--provider-name`` (string)


  The identity provider name.

  

``--provider-type`` (string)


  The identity provider type.

  

  Possible values:

  
  *   ``SAML``

  

  

``--provider-details`` (map)


  The identity provider details, such as ``MetadataURL`` and ``MetadataFile`` .

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--attribute-mapping`` (map)


  A mapping of identity provider attributes to standard and custom user pool attributes.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--idp-identifiers`` (list)


  A list of identity provider identifiers.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IdentityProvider -> (structure)

  

  The newly created identity provider object.

  

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

    

    

  

