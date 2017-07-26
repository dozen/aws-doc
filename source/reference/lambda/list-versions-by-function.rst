[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda list-versions-by-function:


*************************
list-versions-by-function
*************************



===========
Description
===========



List all versions of a function. For information about the versioning feature, see `AWS Lambda Function Versioning and Aliases`_ . 



========
Synopsis
========

::

    list-versions-by-function
  --function-name <value>
  [--marker <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--function-name`` (string)


  Function name whose versions to list. You can specify a function name (for example, ``Thumbnail`` ) or you can specify Amazon Resource Name (ARN) of the function (for example, ``arn:aws:lambda:us-west-2:account-id:function:ThumbNail`` ). AWS Lambda also allows you to specify a partial ARN (for example, ``account-id:Thumbnail`` ). Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 character in length. 

  

``--marker`` (string)


  Optional string. An opaque pagination token returned from a previous ``list-versions-by-function`` operation. If present, indicates where to continue the listing. 

  

``--max-items`` (integer)


  Optional integer. Specifies the maximum number of AWS Lambda function versions to return in response. This parameter value must be greater than 0. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

NextMarker -> (string)

  

  A string, present if there are more function versions.

  

  

Versions -> (list)

  

  A list of Lambda function versions.

  

  (structure)

    

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

        

        

      

    

  



.. _AWS Lambda Function Versioning and Aliases: http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html
