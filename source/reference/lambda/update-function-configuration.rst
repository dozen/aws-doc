[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda update-function-configuration:


*****************************
update-function-configuration
*****************************



===========
Description
===========



Updates the configuration parameters for the specified Lambda function by using the values provided in the request. You provide only the parameters you want to change. This operation must only be used on an existing Lambda function and cannot be used to update the function's code. 

 

If you are using the versioning feature, note this API will always update the $LATEST version of your Lambda function. For information about the versioning feature, see `AWS Lambda Function Versioning and Aliases`_ . 

 

This operation requires permission for the ``lambda:UpdateFunctionConfiguration`` action.



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
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

    

    

  



.. _AWS Lambda Function Versioning and Aliases: http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html
