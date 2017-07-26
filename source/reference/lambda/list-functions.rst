[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda list-functions:


**************
list-functions
**************



===========
Description
===========



Returns a list of your Lambda functions. For each function, the response includes the function configuration information. You must use  get-function to retrieve the code for your function.

 

This operation requires permission for the ``lambda:ListFunctions`` action.

 

If you are using the versioning feature, you can list all of your functions or only ``$LATEST`` versions. For information about the versioning feature, see `AWS Lambda Function Versioning and Aliases <http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/ListFunctions>`_


``list-functions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Functions``


========
Synopsis
========

::

    list-functions
  [--master-region <value>]
  [--function-version <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--master-region`` (string)


  Optional string. If not specified, will return only regular function versions (i.e., non-replicated versions).

   

  Valid values are:

   

  The region from which the functions are replicated. For example, if you specify ``us-east-1`` , only functions replicated from that region will be returned.

   

   ``ALL`` _ Will return all functions from any region. If specified, you also must specify a valid function-version parameter.

  

``--function-version`` (string)


  Optional string. If not specified, only the unqualified functions ARNs (Amazon Resource Names) will be returned.

   

  Valid value:

   

   ``ALL`` _ Will return all versions, including ``$LATEST`` which will have fully qualified ARNs (Amazon Resource Names).

  

  Possible values:

  
  *   ``ALL``

  

  

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextMarker -> (string)

  

  A string, present if there are more functions.

  

  

Functions -> (list)

  

  A list of Lambda functions.

  

  (structure)

    

    A complex type that describes function metadata.

    

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

      

      

    

  

