[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass get-function-definition-version:


*******************************
get-function-definition-version
*******************************



===========
Description
===========

Retrieves information about a Lambda function definition version, such as which Lambda functions are included in the version and their configurations.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/GetFunctionDefinitionVersion>`_


========
Synopsis
========

::

    get-function-definition-version
  --function-definition-id <value>
  --function-definition-version-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--function-definition-id`` (string)
the unique Id of the lambda definition

``--function-definition-version-id`` (string)
Function definition version Id

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Arn -> (string)

  Arn of the function definition version.

  

CreationTimestamp -> (string)

  Timestamp when the funtion definition version was created.

  

Definition -> (structure)

  Information on the function definition version

  Functions -> (list)

    Lambda functions in this function definition version.

    (structure)

      Information on function

      FunctionArn -> (string)

        Arn of the Lambda function.

        

      FunctionConfiguration -> (structure)

        Configuration of the function

        Environment -> (structure)

          Environment of the function configuration

          Variables -> (map)

            Environment variables for the lambda function.

            key -> (string)

              

              

            value -> (string)

              

              

            

          

        ExecArgs -> (string)

          Execution Arguments

          

        Executable -> (string)

          Executable

          

        MemorySize -> (integer)

          The memory size, in KB, you configured for the function.

          

        Pinned -> (boolean)

          Whether the function is pinned or not. Pinned means the function is long-lived and starts when the core starts.

          

        Timeout -> (integer)

          The function execution time at which Lambda should terminate the function. This timeout still applies to pinned lambdas for each request.

          

        

      Id -> (string)

        Id of the function in this version.

        

      

    

  

Id -> (string)

  Id of the function definition the version belongs to.

  

Version -> (string)

  Version of the function definition version.

  

