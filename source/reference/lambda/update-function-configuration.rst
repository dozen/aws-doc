[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda update-function-configuration:


*****************************
update-function-configuration
*****************************



===========
Description
===========



Updates the configuration parameters for the specified Lambda function by using the values provided in the request. You provide only the parameters you want to change. This operation must only be used on an existing Lambda function and cannot be used to update the function's code.

 

If you are using the versioning feature, note this API will always update the $LATEST version of your Lambda function. For information about the versioning feature, see `AWS Lambda Function Versioning and Aliases <http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html>`_ . 

 

This operation requires permission for the ``lambda:UpdateFunctionConfiguration`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/UpdateFunctionConfiguration>`_


========
Synopsis
========

::

    update-function-configuration
  --function-name <value>
  [--role <value>]
  [--handler <value>]
  [--description <value>]
  [--timeout <value>]
  [--memory-size <value>]
  [--vpc-config <value>]
  [--environment <value>]
  [--runtime <value>]
  [--dead-letter-config <value>]
  [--kms-key-arn <value>]
  [--tracing-config <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--function-name`` (string)


  The name of the Lambda function.

   

  You can specify a function name (for example, ``Thumbnail`` ) or you can specify Amazon Resource Name (ARN) of the function (for example, ``arn:aws:lambda:us-west-2:account-id:function:ThumbNail`` ). AWS Lambda also allows you to specify a partial ARN (for example, ``account-id:Thumbnail`` ). Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 character in length. 

  

``--role`` (string)


  The Amazon Resource Name (ARN) of the IAM role that Lambda will assume when it executes your function.

  

``--handler`` (string)


  The function that Lambda calls to begin executing your function. For Node.js, it is the ``module-name.export`` value in your function. 

  

``--description`` (string)


  A short user-defined function description. AWS Lambda does not use this value. Assign a meaningful description as you see fit.

  

``--timeout`` (integer)


  The function execution time at which AWS Lambda should terminate the function. Because the execution time has cost implications, we recommend you set this value based on your expected execution time. The default is 3 seconds.

  

``--memory-size`` (integer)


  The amount of memory, in MB, your Lambda function is given. AWS Lambda uses this memory size to infer the amount of CPU allocated to your function. Your function use-case determines your CPU and memory requirements. For example, a database operation might need less memory compared to an image processing function. The default value is 128 MB. The value must be a multiple of 64 MB.

  

``--vpc-config`` (structure)


  If your Lambda function accesses resources in a VPC, you provide this parameter identifying the list of security group IDs and subnet IDs. These must belong to the same VPC. You must provide at least one security group and one subnet ID.

  



Shorthand Syntax::

    SubnetIds=string,string,SecurityGroupIds=string,string




JSON Syntax::

  {
    "SubnetIds": ["string", ...],
    "SecurityGroupIds": ["string", ...]
  }



``--environment`` (structure)


  The parent object that contains your environment's configuration settings.

  



Shorthand Syntax::

    Variables={KeyName1=string,KeyName2=string}




JSON Syntax::

  {
    "Variables": {"string": "string"
      ...}
  }



``--runtime`` (string)


  The runtime environment for the Lambda function.

   

  To use the Python runtime v3.6, set the value to "python3.6". To use the Python runtime v2.7, set the value to "python2.7". To use the Node.js runtime v6.10, set the value to "nodejs6.10". To use the Node.js runtime v4.3, set the value to "nodejs4.3". To use the Python runtime v3.6, set the value to "python3.6".

   

  .. note::

     

    Node v0.10.42 is currently marked as deprecated. You must migrate existing functions to the newer Node.js runtime versions available on AWS Lambda (nodejs4.3 or nodejs6.10) as soon as possible. You can request a one-time extension until June 30, 2017 by going to the Lambda console and following the instructions provided. Failure to do so will result in an invalid parameter error being returned. Note that you will have to follow this procedure for each region that contains functions written in the Node v0.10.42 runtime.

     

  

  Possible values:

  
  *   ``nodejs``

  
  *   ``nodejs4.3``

  
  *   ``nodejs6.10``

  
  *   ``java8``

  
  *   ``python2.7``

  
  *   ``python3.6``

  
  *   ``dotnetcore1.0``

  
  *   ``nodejs4.3-edge``

  

  

``--dead-letter-config`` (structure)


  The parent object that contains the target ARN (Amazon Resource Name) of an Amazon SQS queue or Amazon SNS topic.

  



Shorthand Syntax::

    TargetArn=string




JSON Syntax::

  {
    "TargetArn": "string"
  }



``--kms-key-arn`` (string)


  The Amazon Resource Name (ARN) of the KMS key used to encrypt your function's environment variables. If you elect to use the AWS Lambda default service key, pass in an empty string ("") for this parameter.

  

``--tracing-config`` (structure)


  The parent object that contains your function's tracing settings.

  



Shorthand Syntax::

    Mode=string




JSON Syntax::

  {
    "Mode": "Active"|"PassThrough"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FunctionName -> (string)

  

  The name of the function. Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 characters in length.

  

  

FunctionArn -> (string)

  

  The Amazon Resource Name (ARN) assigned to the function.

  

  

Runtime -> (string)

  

  The runtime environment for the Lambda function.

  

  

Role -> (string)

  

  The Amazon Resource Name (ARN) of the IAM role that Lambda assumes when it executes your function to access any other Amazon Web Services (AWS) resources.

  

  

Handler -> (string)

  

  The function Lambda calls to begin executing your function.

  

  

CodeSize -> (long)

  

  The size, in bytes, of the function .zip file you uploaded.

  

  

Description -> (string)

  

  The user-provided description.

  

  

Timeout -> (integer)

  

  The function execution time at which Lambda should terminate the function. Because the execution time has cost implications, we recommend you set this value based on your expected execution time. The default is 3 seconds.

  

  

MemorySize -> (integer)

  

  The memory size, in MB, you configured for the function. Must be a multiple of 64 MB.

  

  

LastModified -> (string)

  

  The time stamp of the last time you updated the function. The time stamp is conveyed as a string complying with ISO-8601 in this way YYYY-MM-DDThh:mm:ssTZD (e.g., 1997-07-16T19:20:30+01:00). For more information, see `Date and Time Formats <https://www.w3.org/TR/NOTE-datetime>`_ .

  

  

CodeSha256 -> (string)

  

  It is the SHA256 hash of your function deployment package.

  

  

Version -> (string)

  

  The version of the Lambda function.

  

  

VpcConfig -> (structure)

  

  VPC configuration associated with your Lambda function.

  

  SubnetIds -> (list)

    

    A list of subnet IDs associated with the Lambda function.

    

    (string)

      

      

    

  SecurityGroupIds -> (list)

    

    A list of security group IDs associated with the Lambda function.

    

    (string)

      

      

    

  VpcId -> (string)

    

    The VPC ID associated with you Lambda function.

    

    

  

DeadLetterConfig -> (structure)

  

  The parent object that contains the target ARN (Amazon Resource Name) of an Amazon SQS queue or Amazon SNS topic.

  

  TargetArn -> (string)

    

    The Amazon Resource Name (ARN) of an Amazon SQS queue or Amazon SNS topic you specify as your Dead Letter Queue (DLQ).

    

    

  

Environment -> (structure)

  

  The parent object that contains your environment's configuration settings.

  

  Variables -> (map)

    

    The key-value pairs returned that represent your environment's configuration settings or error information.

    

    key -> (string)

      

      

    value -> (string)

      

      

    

  Error -> (structure)

    

    The parent object that contains error information associated with your configuration settings.

    

    ErrorCode -> (string)

      

      The error code returned by the environment error object.

      

      

    Message -> (string)

      

      The message returned by the environment error object.

      

      

    

  

KMSKeyArn -> (string)

  

  The Amazon Resource Name (ARN) of the KMS key used to encrypt your function's environment variables. If empty, it means you are using the AWS Lambda default service key.

  

  

TracingConfig -> (structure)

  

  The parent object that contains your function's tracing settings.

  

  Mode -> (string)

    

    The tracing mode associated with your Lambda function.

    

    

  

MasterArn -> (string)

  

  Returns the ARN (Amazon Resource Name) of the master function.

  

  

