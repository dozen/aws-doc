[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda publish-version:


***************
publish-version
***************



===========
Description
===========



Publishes a version of your function from the current snapshot of $LATEST. That is, AWS Lambda takes a snapshot of the function code and configuration information from $LATEST and publishes a new version. The code and configuration cannot be modified after publication. For information about the versioning feature, see `AWS Lambda Function Versioning and Aliases <http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/PublishVersion>`_


========
Synopsis
========

::

    publish-version
  --function-name <value>
  [--code-sha-256 <value>]
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--function-name`` (string)


  The Lambda function name. You can specify a function name (for example, ``Thumbnail`` ) or you can specify Amazon Resource Name (ARN) of the function (for example, ``arn:aws:lambda:us-west-2:account-id:function:ThumbNail`` ). AWS Lambda also allows you to specify a partial ARN (for example, ``account-id:Thumbnail`` ). Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 characters in length. 

  

``--code-sha-256`` (string)


  The SHA256 hash of the deployment package you want to publish. This provides validation on the code you are publishing. If you provide this parameter value must match the SHA256 of the $LATEST version for the publication to succeed.

  

``--description`` (string)


  The description for the version you are publishing. If not provided, AWS Lambda copies the description from the $LATEST version.

  

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

  

  

