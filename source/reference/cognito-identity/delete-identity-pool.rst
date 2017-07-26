[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity delete-identity-pool:


********************
delete-identity-pool
********************



===========
Description
===========



Deletes a user pool. Once a pool is deleted, users will not be able to authenticate with the pool.

 

You must use AWS Developer credentials to call this API.



========
Synopsis
========

::

    delete-identity-pool
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

None