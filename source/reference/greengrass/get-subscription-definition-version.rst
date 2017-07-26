[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass get-subscription-definition-version:


***********************************
get-subscription-definition-version
***********************************



===========
Description
===========

Retrieves information about a subscription definition version.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/GetSubscriptionDefinitionVersion>`_


========
Synopsis
========

::

    get-subscription-definition-version
  --subscription-definition-id <value>
  --subscription-definition-version-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subscription-definition-id`` (string)
subscription definition Id

``--subscription-definition-version-id`` (string)
subscription definition version Id

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Arn -> (string)

  Arn of the subscription definition version.

  

CreationTimestamp -> (string)

  Timestamp of when the subscription definition version was created.

  

Definition -> (structure)

  Information on the definition

  Subscriptions -> (list)

    Subscriptions in the version.

    (structure)

      Information on subscription

      Id -> (string)

        Element Id for this entry in the list.

        

      Source -> (string)

        Source of the subscription. Can be a thing arn, lambda arn or word 'cloud'

        

      Subject -> (string)

        Subject of the message.

        

      Target -> (string)

        Where the message is sent to. Can be a thing arn, lambda arn or word 'cloud'.

        

      

    

  

Id -> (string)

  Id of the subscription definition the version belongs to.

  

Version -> (string)

  Version of the subscription definition version.

  

