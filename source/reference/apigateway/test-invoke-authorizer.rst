[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway test-invoke-authorizer:


**********************
test-invoke-authorizer
**********************



===========
Description
===========



Simulate the execution of an  Authorizer in your  RestApi with headers, parameters, and an incoming request body.

  `Enable custom authorizers <http://docs.aws.amazon.com/apigateway/latest/developerguide/use-custom-authorizer.html>`_  

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/TestInvokeAuthorizer>`_


========
Synopsis
========

::

    test-invoke-authorizer
  --rest-api-id <value>
  --authorizer-id <value>
  [--headers <value>]
  [--path-with-query-string <value>]
  [--body <value>]
  [--stage-variables <value>]
  [--additional-context <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--authorizer-id`` (string)


  Specifies a test invoke authorizer request's  Authorizer ID.

  

``--headers`` (map)


  [Required] A key-value map of headers to simulate an incoming invocation request. This is where the incoming authorization token, or identity source, should be specified.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--path-with-query-string`` (string)


  [Optional] The URI path, including query string, of the simulated invocation request. Use this to specify path parameters and query string parameters.

  

``--body`` (string)


  [Optional] The simulated request body of an incoming invocation request.

  

``--stage-variables`` (map)


  A key-value map of stage variables to simulate an invocation on a deployed  Stage .

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--additional-context`` (map)


  [Optional] A key-value map of additional context variables.

  



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

**To test invoke a request to a Custom Authorizer including the required header and value**

Command::

  aws apigateway test-invoke-authorizer --rest-api-id 1234123412 --authorizer-id 5yid1t --headers Authorization='Value'


======
Output
======

clientStatus -> (integer)

  

  The HTTP status code that the client would have received. Value is 0 if the authorizer succeeded.

  

  

log -> (string)

  

  The Amazon API Gateway execution log for the test authorizer request.

  

  

latency -> (long)

  

  The execution latency of the test authorizer request.

  

  

principalId -> (string)

  

  The principal identity returned by the  Authorizer 

  

  

policy -> (string)

  

  The JSON policy document returned by the  Authorizer 

  

  

authorization -> (map)

  

  key -> (string)

    

    

  value -> (list)

    

    (string)

      

      

    

  

claims -> (map)

  

  The `open identity claims <http://openid.net/specs/openid-connect-core-1_0.html#StandardClaims>`_ , with any supported custom attributes, returned from the Cognito Your User Pool configured for the API.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

