[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity unlink-identity:


***************
unlink-identity
***************



===========
Description
===========



Unlinks a federated identity from an existing account. Unlinked logins will be considered new identities next time they are seen. Removing the last linked login will make this identity inaccessible.

 

This is a public API. You do not need any credentials to call this API.



========
Synopsis
========

::

    unlink-identity
  --identity-id <value>
  --logins <value>
  --logins-to-remove <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-id`` (string)
A unique identifier in the format REGION:GUID.

``--logins`` (map)
A set of optional name-value pairs that map provider names to provider tokens.



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--logins-to-remove`` (list)
Provider names to unlink from this identity.



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None