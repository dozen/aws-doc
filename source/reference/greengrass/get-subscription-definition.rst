[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass get-subscription-definition:


***************************
get-subscription-definition
***************************



===========
Description
===========

Retrieves information about a subscription definition.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/GetSubscriptionDefinition>`_


========
Synopsis
========

::

    get-subscription-definition
  --subscription-definition-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subscription-definition-id`` (string)
subscription definition Id

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

  

