[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity get-identity-pool-roles:


***********************
get-identity-pool-roles
***********************



===========
Description
===========



Gets the roles for an identity pool.

 

You must use AWS Developer credentials to call this API.



========
Synopsis
========

::

    get-identity-pool-roles
  --identity-pool-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-pool-id`` (string)


  An identity pool ID in the format REGION:GUID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

IdentityPoolId -> (string)

  

  An identity pool ID in the format REGION:GUID.

  

  

Roles -> (map)

  

  The map of roles associated with this pool. Currently only authenticated and unauthenticated roles are supported.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

