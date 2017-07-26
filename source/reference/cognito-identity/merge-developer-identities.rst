[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity merge-developer-identities:


**************************
merge-developer-identities
**************************



===========
Description
===========



Merges two users having different ``IdentityId`` s, existing in the same identity pool, and identified by the same developer provider. You can use this action to request that discrete users be merged and identified as a single user in the Cognito environment. Cognito associates the given source user (``SourceUserIdentifier`` ) with the ``IdentityId`` of the ``DestinationUserIdentifier`` . Only developer-authenticated users can be merged. If the users to be merged are associated with the same public provider, but as two different users, an exception will be thrown.

 

You must use AWS Developer credentials to call this API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-identity-2014-06-30/MergeDeveloperIdentities>`_


========
Synopsis
========

::

    merge-developer-identities
  --source-user-identifier <value>
  --destination-user-identifier <value>
  --developer-provider-name <value>
  --identity-pool-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-user-identifier`` (string)


  User identifier for the source user. The value should be a ``source-user-identifier`` .

  

``--destination-user-identifier`` (string)


  User identifier for the destination user. The value should be a ``source-user-identifier`` .

  

``--developer-provider-name`` (string)


  The "domain" by which Cognito will refer to your users. This is a (pseudo) domain name that you provide while creating an identity pool. This name acts as a placeholder that allows your backend and the Cognito service to communicate about the developer provider. For the ``developer-provider-name`` , you can use letters as well as period (.), underscore (_), and dash (-).

  

``--identity-pool-id`` (string)


  An identity pool ID in the format REGION:GUID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IdentityId -> (string)

  

  A unique identifier in the format REGION:GUID.

  

  

