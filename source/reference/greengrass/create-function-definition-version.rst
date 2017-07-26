[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass create-function-definition-version:


**********************************
create-function-definition-version
**********************************



===========
Description
===========

Create a version of a Lambda function definition that has already been defined.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/CreateFunctionDefinitionVersion>`_


========
Synopsis
========

::

    create-function-definition-version
  [--amzn-client-token <value>]
  --function-definition-id <value>
  [--functions <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--amzn-client-token`` (string)
The client token used to request idempotent operations.

``--function-definition-id`` (string)
the unique Id of the lambda definition

``--functions`` (list)
Lambda functions in this function definition version.



Shorthand Syntax::

    FunctionArn=string,FunctionConfiguration={Environment={Variables={KeyName1=string,KeyName2=string}},ExecArgs=string,Executable=string,MemorySize=integer,Pinned=boolean,Timeout=integer},Id=string ...




JSON Syntax::

  [
    {
      "FunctionArn": "string",
      "FunctionConfiguration": {
        "Environment": {
          "Variables": {"string": "string"
            ...}
        },
        "ExecArgs": "string",
        "Executable": "string",
        "MemorySize": integer,
        "Pinned": true|false,
        "Timeout": integer
      },
      "Id": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Arn -> (string)

  Arn of the version.

  

CreationTimestamp -> (string)

  Timestamp of when the version was created.

  

Id -> (string)

  Id of the resource container.

  

Version -> (string)

  Unique Id of a version.

  

