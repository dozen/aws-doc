[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway delete-method-response:


**********************
delete-method-response
**********************



===========
Description
===========



Deletes an existing  MethodResponse resource.



========
Synopsis
========

::

    delete-method-response
  --rest-api-id <value>
  --resource-id <value>
  --http-method <value>
  --status-code <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  The  RestApi identifier for the  MethodResponse resource.

  

``--resource-id`` (string)


  The  Resource identifier for the  MethodResponse resource.

  

``--http-method`` (string)


  The HTTP verb identifier for the parent  Method resource.

  

``--status-code`` (string)


  The status code identifier for the  MethodResponse resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None