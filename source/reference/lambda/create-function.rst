[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda create-function:


***************
create-function
***************



===========
Description
===========



Creates a new Lambda function. The function metadata is created from the request parameters, and the code for the function is provided by a .zip file in the request body. If the function name already exists, the operation will fail. Note that the function name is case-sensitive. 

 

If you are using versioning, you can also publish a version of the Lambda function you are creating using the ``Publish`` parameter. For more information about versioning, see `AWS Lambda Function Versioning and Aliases`_ . 

 

This operation requires permission for the ``lambda:CreateFunction`` action.



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
  [--zip-file <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--function-name`` (string)


  The name you want to assign to the function you are uploading. The function names appear in the console and are returned in the  list-functions API. Function names are used to specify functions to other AWS Lambda APIs, such as  invoke . 

  

``--runtime`` (string)


  The runtime environment for the Lambda function you are uploading. 

  

  Possible values:

  
  *   ``nodejs``

  
  *   ``java8``

  
  *   ``python2.7``

  

  

``--role`` (string)


  The Amazon Resource Name (ARN) of the IAM role that Lambda assumes when it executes your function to access any other Amazon Web Services (AWS) resources. For more information, see `AWS Lambda\: How it Works`_ . 

  

``--handler`` (string)


  The function within your code that Lambda calls to begin execution. For Node.js, it is the *module-name* .*export* value in your function. For Java, it can be ``package.class-name::handler`` or ``package.class-name`` . For more information, see `Lambda Function handler (Java)`_ . 

  

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



``--zip-file`` (blob)


  The path to the zip file of the code you are uploading. Example: fileb://code.zip

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

FunctionName -> (string)

  

  The name of the function.

  

  

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

  

  The time stamp of the last time you updated the function.

  

  

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

    

    

  



.. _AWS Lambda\: How it Works: http://docs.aws.amazon.com/lambda/latest/dg/lambda-introduction.html
.. _AWS Lambda Function Versioning and Aliases: http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html
.. _Lambda Function handler (Java): http://docs.aws.amazon.com/lambda/latest/dg/java-programming-model-handler-types.html
