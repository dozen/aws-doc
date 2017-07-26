[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda get-function:


************
get-function
************



===========
Description
===========



Returns the configuration information of the Lambda function and a presigned URL link to the .zip file you uploaded with  create-function so you can download the .zip file. Note that the URL is valid for up to 10 minutes. The configuration information is the same information you provided as parameters when uploading the function.

 

Using the optional ``qualifier`` parameter, you can specify a specific function version for which you want this information. If you don't specify this parameter, the API uses unqualified function ARN which return information about the ``$LATEST`` version of the Lambda function. For more information, see `AWS Lambda Function Versioning and Aliases`_ .

 

This operation requires permission for the ``lambda:GetFunction`` action.



========
Synopsis
========

::

    get-function
  --function-name <value>
  [--qualifier <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--function-name`` (string)


  The Lambda function name. 

   

  You can specify a function name (for example, ``Thumbnail`` ) or you can specify Amazon Resource Name (ARN) of the function (for example, ``arn:aws:lambda:us-west-2:account-id:function:ThumbNail`` ). AWS Lambda also allows you to specify a partial ARN (for example, ``account-id:Thumbnail`` ). Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 character in length. 

  

``--qualifier`` (string)


  Using this optional parameter to specify a function version or an alias name. If you specify function version, the API uses qualified function ARN for the request and returns information about the specific Lambda function version. If you specify an alias name, the API uses the alias ARN and returns information about the function version to which the alias points. If you don't provide this parameter, the API uses unqualified function ARN and returns information about the ``$LATEST`` version of the Lambda function.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Configuration -> (structure)

  

  A complex type that describes function metadata.

  

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

      

      

    

  

Code -> (structure)

  

  The object for the Lambda function location.

  

  RepositoryType -> (string)

    

    The repository from which you can download the function.

    

    

  Location -> (string)

    

    The presigned URL you can use to download the function's .zip file that you previously uploaded. The URL is valid for up to 10 minutes.

    

    

  



.. _AWS Lambda Function Versioning and Aliases: http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html
