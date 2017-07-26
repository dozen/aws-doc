[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway test-invoke-method:


******************
test-invoke-method
******************



===========
Description
===========



========
Synopsis
========

::

    test-invoke-method
  --rest-api-id <value>
  --resource-id <value>
  --http-method <value>
  [--path-with-query-string <value>]
  [--body <value>]
  [--headers <value>]
  [--client-certificate-id <value>]
  [--stage-variables <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


``--resource-id`` (string)


``--http-method`` (string)


``--path-with-query-string`` (string)


``--body`` (string)


``--headers`` (map)




Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--client-certificate-id`` (string)


``--stage-variables`` (map)




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

status -> (integer)

  

  The HTTP status code.

  

  

body -> (string)

  

  The body of HTTP response.

  

  

headers -> (map)

  

  The headers of HTTP response.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

log -> (string)

  

  The Amazon API Gateway execution log for the test invoke request.

  

  

latency -> (long)

  

  The execution latency of the test invoke request.

  

  

