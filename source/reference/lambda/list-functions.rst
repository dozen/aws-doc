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

 

If you are using versioning feature, the response returns list of $LATEST versions of your functions. For information about the versioning feature, see `AWS Lambda Function Versioning and Aliases`_ . 



``list-functions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Functions``


========
Synopsis
========

::

    list-functions
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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
