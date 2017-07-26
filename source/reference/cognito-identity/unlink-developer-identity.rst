[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity unlink-developer-identity:


*************************
unlink-developer-identity
*************************



===========
Description
===========



Unlinks a ``developer-user-identifier`` from an existing identity. Unlinked developer users will be considered new identities next time they are seen. If, for a given Cognito identity, you remove all federated identities as well as the developer user identifier, the Cognito identity becomes inaccessible.

 

You must use AWS Developer credentials to call this API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-identity-2014-06-30/UnlinkDeveloperIdentity>`_


========
Synopsis
========

::

    unlink-developer-identity
  --identity-id <value>
  --identity-pool-id <value>
  --developer-provider-name <value>
  --developer-user-identifier <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-id`` (string)


  A unique identifier in the format REGION:GUID.

  

``--identity-pool-id`` (string)


  An identity pool ID in the format REGION:GUID.

  

``--developer-provider-name`` (string)


  The "domain" by which Cognito will refer to your users.

  

``--developer-user-identifier`` (string)


  A unique ID used by your backend authentication process to identify a user.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None