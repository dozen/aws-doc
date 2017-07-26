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
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None