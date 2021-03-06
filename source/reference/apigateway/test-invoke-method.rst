[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway test-invoke-method:


******************
test-invoke-method
******************



===========
Description
===========



Simulate the execution of a  Method in your  RestApi with headers, parameters, and an incoming request body.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/TestInvokeMethod>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--resource-id`` (string)


  Specifies a test invoke method request's resource ID.

  

``--http-method`` (string)


  Specifies a test invoke method request's HTTP method.

  

``--path-with-query-string`` (string)


  The URI path, including query string, of the simulated invocation request. Use this to specify path parameters and query string parameters.

  

``--body`` (string)


  The simulated request body of an incoming invocation request.

  

``--headers`` (map)


  A key-value map of headers to simulate an incoming invocation request.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--client-certificate-id`` (string)


  A  ClientCertificate identifier to use in the test invocation. API Gateway will use the certificate when making the HTTPS request to the defined back-end endpoint.

  

``--stage-variables`` (map)


  A key-value map of stage variables to simulate an invocation on a deployed  Stage .

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To test invoke the root resource in an API by making a GET request**

Command::

  aws apigateway test-invoke-method --rest-api-id 1234123412 --resource-id avl5sg8fw8 --http-method GET --path-with-query-string '/'

**To test invoke a sub-resource in an API by making a GET request with a path parameter value specified**

Command::

  aws apigateway test-invoke-method --rest-api-id 1234123412 --resource-id 3gapai --http-method GET --path-with-query-string '/pets/1'


======
Output
======

status -> (integer)

  

  The HTTP status code.

  

  

body -> (string)

  

  The body of the HTTP response.

  

  

headers -> (map)

  

  The headers of the HTTP response.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

log -> (string)

  

  The Amazon API Gateway execution log for the test invoke request.

  

  

latency -> (long)

  

  The execution latency of the test invoke request.

  

  

