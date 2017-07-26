[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass create-logger-definition-version:


********************************
create-logger-definition-version
********************************



===========
Description
===========

Creates a version of a logger definition that has already been defined.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/CreateLoggerDefinitionVersion>`_


========
Synopsis
========

::

    create-logger-definition-version
  [--amzn-client-token <value>]
  --logger-definition-id <value>
  [--loggers <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--amzn-client-token`` (string)
The client token used to request idempotent operations.

``--logger-definition-id`` (string)
logger definition Id

``--loggers`` (list)
List of loggers.



Shorthand Syntax::

    Component=string,Id=string,Level=string,Space=integer,Type=string ...




JSON Syntax::

  [
    {
      "Component": "GreengrassSystem"|"Lambda",
      "Id": "string",
      "Level": "DEBUG"|"INFO"|"WARN"|"ERROR"|"FATAL",
      "Space": integer,
      "Type": "FileSystem"|"AWSCloudWatch"
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

  

