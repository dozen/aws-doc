[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass create-group-version:


********************
create-group-version
********************



===========
Description
===========

Creates a version of a group which has already been defined.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/CreateGroupVersion>`_


========
Synopsis
========

::

    create-group-version
  [--amzn-client-token <value>]
  [--core-definition-version-arn <value>]
  [--device-definition-version-arn <value>]
  [--function-definition-version-arn <value>]
  --group-id <value>
  [--logger-definition-version-arn <value>]
  [--subscription-definition-version-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--amzn-client-token`` (string)
The client token used to request idempotent operations.

``--core-definition-version-arn`` (string)
Core definition version arn for this group.

``--device-definition-version-arn`` (string)
Device definition version arn for this group.

``--function-definition-version-arn`` (string)
Function definition version arn for this group.

``--group-id`` (string)
The unique Id of the AWS Greengrass Group

``--logger-definition-version-arn`` (string)
Logger definitionv ersion arn for this group.

``--subscription-definition-version-arn`` (string)
Subscription definition version arn for this group.

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

  

