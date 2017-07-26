[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass create-logger-definition:


************************
create-logger-definition
************************



===========
Description
===========

Creates a logger definition. You may optionally provide the initial version of the logger definition or use ``CreateLoggerDefinitionVersion`` at a later time.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/CreateLoggerDefinition>`_


========
Synopsis
========

::

    create-logger-definition
  [--amzn-client-token <value>]
  [--initial-version <value>]
  [--name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--amzn-client-token`` (string)
The client token used to request idempotent operations.

``--initial-version`` (structure)
Information on the initial version



Shorthand Syntax::

    Loggers=[{Component=string,Id=string,Level=string,Space=integer,Type=string},{Component=string,Id=string,Level=string,Space=integer,Type=string}]




JSON Syntax::

  {
    "Loggers": [
      {
        "Component": "GreengrassSystem"|"Lambda",
        "Id": "string",
        "Level": "DEBUG"|"INFO"|"WARN"|"ERROR"|"FATAL",
        "Space": integer,
        "Type": "FileSystem"|"AWSCloudWatch"
      }
      ...
    ]
  }



``--name`` (string)
name of the logger definition

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Arn -> (string)

  Arn of the definition.

  

CreationTimestamp -> (string)

  Timestamp of when the definition was created.

  

Id -> (string)

  Id of the definition.

  

LastUpdatedTimestamp -> (string)

  Last updated timestamp of the definition.

  

LatestVersion -> (string)

  Last version of the definition.

  

LatestVersionArn -> (string)

  Latest version arn of the definition.

  

Name -> (string)

  Name of the definition.

  

