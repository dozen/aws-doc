[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda create-function:


***************
create-function
***************



===========
Description
===========



Creates a new Lambda function. The function metadata is created from the request parameters, and the code for the function is provided by a .zip file in the request body. If the function name already exists, the operation will fail. Note that the function name is case-sensitive.

 

If you are using versioning, you can also publish a version of the Lambda function you are creating using the ``Publish`` parameter. For more information about versioning, see `AWS Lambda Function Versioning and Aliases <http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html>`_ . 

 

This operation requires permission for the ``lambda:CreateFunction`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/CreateFunction>`_


========
Synopsis
========

::

    create-function
  --function-name <value>
  --runtime <value>
  --role <value>
  --handler <value>
  [--code <value>]
  [--description <value>]
  [--timeout <value>]
  [--memory-size <value>]
  [--publish | --no-publish]
  [--vpc-config <value>]
  [--dead-letter-config <value>]
  [--environment <value>]
  [--kms-key-arn <value>]
  [--tracing-config <value>]
  [--tags <value>]
  [--zip-file <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--function-name`` (string)


  The name you want to assign to the function you are uploading. The function names appear in the console and are returned in the  list-functions API. Function names are used to specify functions to other AWS Lambda API operations, such as  invoke . Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 characters in length. 

  

``--runtime`` (string)


  The runtime environment for the Lambda function you are uploading.

   

  To use the Python runtime v3.6, set the value to "python3.6". To use the Python runtime v2.7, set the value to "python2.7". To use the Node.js runtime v6.10, set the value to "nodejs6.10". To use the Node.js runtime v4.3, set the value to "nodejs4.3".

   

  .. note::

     

    Node v0.10.42 is currently marked as deprecated. You must migrate existing functions to the newer Node.js runtime versions available on AWS Lambda (nodejs4.3 or nodejs6.10) as soon as possible. You can request a one-time extension until June 30, 2017 by going to the Lambda console and following the instructions provided. Failure to do so will result in an invalid parmaeter error being returned. Note that you will have to follow this procedure for each region that contains functions written in the Node v0.10.42 runtime.

     

  

  Possible values:

  
  *   ``nodejs``

  
  *   ``nodejs4.3``

  
  *   ``nodejs6.10``

  
  *   ``java8``

  
  *   ``python2.7``

  
  *   ``python3.6``

  
  *   ``dotnetcore1.0``

  
  *   ``nodejs4.3-edge``

  

  

``--role`` (string)


  The Amazon Resource Name (ARN) of the IAM role that Lambda assumes when it executes your function to access any other Amazon Web Services (AWS) resources. For more information, see `AWS Lambda\: How it Works <http://docs.aws.amazon.com/lambda/latest/dg/lambda-introduction.html>`_ . 

  

``--handler`` (string)


  The function within your code that Lambda calls to begin execution. For Node.js, it is the *module-name* .*export* value in your function. For Java, it can be ``package.class-name::handler`` or ``package.class-name`` . For more information, see `Lambda Function handler (Java) <http://docs.aws.amazon.com/lambda/latest/dg/java-programming-model-handler-types.html>`_ . 

  

``--code`` (structure)


  The code for the Lambda function.

  



Shorthand Syntax::

    S3Bucket=string,S3Key=string,S3ObjectVersion=string




JSON Syntax::

  {
    "S3Bucket": "string",
    "S3Key": "string",
    "S3ObjectVersion": "string"
  }



``--description`` (string)


  A short, user-defined function description. Lambda does not use this value. Assign a meaningful description as you see fit.

  

``--timeout`` (integer)


  The function execution time at which Lambda should terminate the function. Because the execution time has cost implications, we recommend you set this value based on your expected execution time. The default is 3 seconds.

  

``--memory-size`` (integer)


  The amount of memory, in MB, your Lambda function is given. Lambda uses this memory size to infer the amount of CPU and memory allocated to your function. Your function use-case determines your CPU and memory requirements. For example, a database operation might need less memory compared to an image processing function. The default value is 128 MB. The value must be a multiple of 64 MB.

  

``--publish`` | ``--no-publish`` (boolean)


  This boolean parameter can be used to request AWS Lambda to create the Lambda function and publish a version as an atomic operation.

  

``--vpc-config`` (structure)


  If your Lambda function accesses resources in a VPC, you provide this parameter identifying the list of security group IDs and subnet IDs. These must belong to the same VPC. You must provide at least one security group and one subnet ID.

  



Shorthand Syntax::

    SubnetIds=string,string,SecurityGroupIds=string,string




JSON Syntax::

  {
    "SubnetIds": ["string", ...],
    "SecurityGroupIds": ["string", ...]
  }



``--dead-letter-config`` (structure)


  The parent object that contains the target ARN (Amazon Resource Name) of an Amazon SQS queue or Amazon SNS topic. 

  



Shorthand Syntax::

    TargetArn=string




JSON Syntax::

  {
    "TargetArn": "string"
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



``--kms-key-arn`` (string)


  The Amazon Resource Name (ARN) of the KMS key used to encrypt your function's environment variables. If not provided, AWS Lambda will use a default service key.

  

``--tracing-config`` (structure)


  The parent object that contains your function's tracing settings.

  



Shorthand Syntax::

    Mode=string




JSON Syntax::

  {
    "Mode": "Active"|"PassThrough"
  }



``--tags`` (map)


  The list of tags (key-value pairs) assigned to the new function.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--zip-file`` (blob)


  The path to the zip file of the code you are uploading. Example: fileb://code.zip

  

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

  

  

