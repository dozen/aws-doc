[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity set-identity-pool-roles:


***********************
set-identity-pool-roles
***********************



===========
Description
===========



Sets the roles for an identity pool. These roles are used when making calls to ``get-credentials-for-identity`` action.

 

You must use AWS Developer credentials to call this API.



========
Synopsis
========

::

    set-identity-pool-roles
  --identity-pool-id <value>
  --roles <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-pool-id`` (string)


  An identity pool ID in the format REGION:GUID.

  

``--roles`` (map)


  The map of roles associated with this pool. For a given role, the key will be either "authenticated" or "unauthenticated" and the value will be the Role ARN.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None