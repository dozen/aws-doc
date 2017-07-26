[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda invoke:


******
invoke
******



===========
Description
===========



Invokes a specific Lambda function. 

 

If you are using the versioning feature, you can invoke the specific function version by providing function version or alias name that is pointing to the function version using the ``qualifier`` parameter in the request. If you don't provide the ``qualifier`` parameter, the ``$LATEST`` version of the Lambda function is invoked. For information about the versioning feature, see `AWS Lambda Function Versioning and Aliases`_ . 

 

This operation requires permission for the ``lambda:InvokeFunction`` action.



========
Synopsis
========

::

    invoke
  --function-name <value>
  [--invocation-type <value>]
  [--log-type <value>]
  [--client-context <value>]
  [--payload <value>]
  [--qualifier <value>]
  outfile <value>




=======
Options
=======

``--function-name`` (string)


  The Lambda function name. 

   

  You can specify a function name (for example, ``Thumbnail`` ) or you can specify Amazon Resource Name (ARN) of the function (for example, ``arn:aws:lambda:us-west-2:account-id:function:ThumbNail`` ). AWS Lambda also allows you to specify a partial ARN (for example, ``account-id:Thumbnail`` ). Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 character in length. 

  

``--invocation-type`` (string)


  By default, the ``invoke`` API assumes ``RequestResponse`` invocation type. You can optionally request asynchronous execution by specifying ``Event`` as the ``invocation-type`` . You can also use this parameter to request AWS Lambda to not execute the function but do some verification, such as if the caller is authorized to invoke the function and if the inputs are valid. You request this by specifying ``DryRun`` as the ``invocation-type`` . This is useful in a cross-account scenario when you want to verify access to a function without running it. 

  

  Possible values:

  
  *   ``Event``

  
  *   ``RequestResponse``

  
  *   ``DryRun``

  

  

``--log-type`` (string)


  You can set this optional parameter to ``Tail`` in the request only if you specify the ``invocation-type`` parameter with value ``RequestResponse`` . In this case, AWS Lambda returns the base64-encoded last 4 KB of log data produced by your Lambda function in the ``x-amz-log-results`` header. 

  

  Possible values:

  
  *   ``None``

  
  *   ``Tail``

  

  

``--client-context`` (string)


  Using the ``ClientContext`` you can pass client-specific information to the Lambda function you are invoking. You can then process the client information in your Lambda function as you choose through the context variable. For an example of a ``ClientContext`` JSON, see `PutEvents`_ in the *Amazon Mobile Analytics API Reference and User Guide* .

   

  The ClientContext JSON must be base64-encoded.

  

``--payload`` (blob)


  JSON that you want to provide to your Lambda function as input.

  

``--qualifier`` (string)


  You can use this optional parameter to specify a Lambda function version or alias name. If you specify a function version, the API uses the qualified function ARN to invoke a specific Lambda function. If you specify an alias name, the API uses the alias ARN to invoke the Lambda function version to which the alias points.

   

  If you don't provide this parameter, then the API uses unqualified function ARN which results in invocation of the ``$LATEST`` version.

  

``outfile`` (string)
Filename where the content will be saved



======
Output
======

StatusCode -> (integer)

  

  The HTTP status code will be in the 200 range for successful request. For the ``RequestResonse`` invocation type this status code will be 200. For the ``Event`` invocation type this status code will be 202. For the ``DryRun`` invocation type the status code will be 204. 

  

  

FunctionError -> (string)

  

  Indicates whether an error occurred while executing the Lambda function. If an error occurred this field will have one of two values; ``Handled`` or ``Unhandled`` . ``Handled`` errors are errors that are reported by the function while the ``Unhandled`` errors are those detected and reported by AWS Lambda. Unhandled errors include out of memory errors and function timeouts. For information about how to report an ``Handled`` error, see `Programming Model`_ . 

  

  

LogResult -> (string)

  

  It is the base64-encoded logs for the Lambda function invocation. This is present only if the invocation type is ``RequestResponse`` and the logs were requested. 

  

  

Payload -> (blob)

  

  It is the JSON representation of the object returned by the Lambda function. In This is present only if the invocation type is ``RequestResponse`` . 

   

  In the event of a function error this field contains a message describing the error. For the ``Handled`` errors the Lambda function will report this message. For ``Unhandled`` errors AWS Lambda reports the message. 

  

  



.. _PutEvents: http://docs.aws.amazon.com/mobileanalytics/latest/ug/PutEvents.html
.. _AWS Lambda Function Versioning and Aliases: http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html
.. _Programming Model: http://docs.aws.amazon.com/lambda/latest/dg/programming-model.html
