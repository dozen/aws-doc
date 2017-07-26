[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass get-group-version:


*****************
get-group-version
*****************



===========
Description
===========

Retrieves information about a group version.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/GetGroupVersion>`_


========
Synopsis
========

::

    get-group-version
  --group-id <value>
  --group-version-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--group-id`` (string)
The unique Id of the AWS Greengrass Group

``--group-version-id`` (string)
Group version Id

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Arn -> (string)

  Arn of the group version.

  

CreationTimestamp -> (string)

  Timestamp when the group version was created.

  

Definition -> (structure)

  Information on the definition

  CoreDefinitionVersionArn -> (string)

    Core definition version arn for this group.

    

  DeviceDefinitionVersionArn -> (string)

    Device definition version arn for this group.

    

  FunctionDefinitionVersionArn -> (string)

    Function definition version arn for this group.

    

  LoggerDefinitionVersionArn -> (string)

    Logger definitionv ersion arn for this group.

    

  SubscriptionDefinitionVersionArn -> (string)

    Subscription definition version arn for this group.

    

  

Id -> (string)

  Id of the group version.

  

Version -> (string)

  Unique Id for a version of the Group.

  

