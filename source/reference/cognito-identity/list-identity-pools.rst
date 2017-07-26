[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity list-identity-pools:


*******************
list-identity-pools
*******************



===========
Description
===========



Lists all of the Cognito identity pools registered for your account.

 

You must use AWS Developer credentials to call this API.



========
Synopsis
========

::

    list-identity-pools
  --max-results <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--max-results`` (integer)
The maximum number of identities to return.

``--next-token`` (string)
A pagination token.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

IdentityPools -> (list)

  The identity pools returned by the list-identity-pools action.

  (structure)

    A description of the identity pool.

    IdentityPoolId -> (string)

      An identity pool ID in the format REGION:GUID.

      

    IdentityPoolName -> (string)

      A string that you provide.

      

    

  

NextToken -> (string)

  A pagination token.

  

