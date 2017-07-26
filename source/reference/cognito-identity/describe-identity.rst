[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity describe-identity:


*****************
describe-identity
*****************



===========
Description
===========



Returns metadata related to the given identity, including when the identity was created and any associated linked logins.

 

You must use AWS Developer credentials to call this API.



========
Synopsis
========

::

    describe-identity
  --identity-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-id`` (string)


  A unique identifier in the format REGION:GUID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

IdentityId -> (string)

  A unique identifier in the format REGION:GUID.

  

Logins -> (list)

  A set of optional name-value pairs that map provider names to provider tokens.

  (string)

    

    

  

CreationDate -> (timestamp)

  

  Date on which the identity was created.

  

  

LastModifiedDate -> (timestamp)

  

  Date on which the identity was last modified.

  

  

