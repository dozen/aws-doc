[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass get-logger-definition-version:


*****************************
get-logger-definition-version
*****************************



===========
Description
===========

Retrieves information about a logger definition version.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/GetLoggerDefinitionVersion>`_


========
Synopsis
========

::

    get-logger-definition-version
  --logger-definition-id <value>
  --logger-definition-version-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--logger-definition-id`` (string)
logger definition Id

``--logger-definition-version-id`` (string)
logger definition version Id

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Arn -> (string)

  Arn of the logger definition version.

  

CreationTimestamp -> (string)

  Timestamp of when the logger definition version was created.

  

Definition -> (structure)

  Information on definition

  Loggers -> (list)

    List of loggers.

    (structure)

      Information on the Logger

      Component -> (string)

        The component that will be subject to logs

        

      Id -> (string)

        Element Id for this entry in the list.

        

      Level -> (string)

        The level of the logs

        

      Space -> (integer)

        Amount of hardware space, in KB, to use if file system is used for logging purposes.

        

      Type -> (string)

        The type which will be use for log output

        

      

    

  

Id -> (string)

  Id of the logger definition the version belongs to.

  

Version -> (string)

  Version of the logger definition version.

  

