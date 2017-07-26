[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda get-account-settings:


********************
get-account-settings
********************



===========
Description
===========



Returns a customer's account settings.

 

You can use this operation to retrieve Lambda limits information, such as code size and concurrency limits. For more information about limits, see `AWS Lambda Limits <http://docs.aws.amazon.com/lambda/latest/dg/limits.html>`_ . You can also retrieve resource usage statistics, such as code storage usage and function count.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/GetAccountSettings>`_


========
Synopsis
========

::

    get-account-settings
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AccountLimit -> (structure)

  

  Provides limits of code size and concurrency associated with the current account and region.

  

  TotalCodeSize -> (long)

    

    Maximum size, in bytes, of a code package you can upload per region. The default size is 75 GB. 

    

    

  CodeSizeUnzipped -> (long)

    

    Size, in bytes, of code/dependencies that you can zip into a deployment package (uncompressed zip/jar size) for uploading. The default limit is 250 MB.

    

    

  CodeSizeZipped -> (long)

    

    Size, in bytes, of a single zipped code/dependencies package you can upload for your Lambda function(.zip/.jar file). Try using Amazon S3 for uploading larger files. Default limit is 50 MB.

    

    

  ConcurrentExecutions -> (integer)

    

    Number of simultaneous executions of your function per region. For more information or to request a limit increase for concurrent executions, see `Lambda Function Concurrent Executions <http://docs.aws.amazon.com/lambda/latest/dg/concurrent-executions.html>`_ . The default limit is 100.

    

    

  

AccountUsage -> (structure)

  

  Provides code size usage and function count associated with the current account and region.

  

  TotalCodeSize -> (long)

    

    Total size, in bytes, of the account's deployment packages per region.

    

    

  FunctionCount -> (long)

    

    The number of your account's existing functions per region.

    

    

  

