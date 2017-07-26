[ :ref:`aws <cli:aws>` . :ref:`cognito-sync <cli:aws cognito-sync>` ]

.. _cli:aws cognito-sync get-cognito-events:


******************
get-cognito-events
******************



===========
Description
===========



Gets the events and the corresponding Lambda functions associated with an identity pool.

 

This API can only be called with developer credentials. You cannot call this API with the temporary user credentials provided by Cognito Identity.



========
Synopsis
========

::

    get-cognito-events
  --identity-pool-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-pool-id`` (string)


  The Cognito Identity Pool ID for the request

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Events -> (map)

  

  The Cognito Events returned from the get-cognito-events request

  

  key -> (string)

    

    

  value -> (string)

    

    

  

