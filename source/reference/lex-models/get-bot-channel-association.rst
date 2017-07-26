[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-bot-channel-association:


***************************
get-bot-channel-association
***************************



===========
Description
===========



Returns information about the association between an Amazon Lex bot and a messaging platform.

 

This operation requires permissions for the ``lex:GetBotChannelAssociation`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetBotChannelAssociation>`_


========
Synopsis
========

::

    get-bot-channel-association
  --name <value>
  --bot-name <value>
  --bot-alias <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the association between the bot and the channel. The name is case sensitive. 

  

``--bot-name`` (string)


  The name of the Amazon Lex bot.

  

``--bot-alias`` (string)


  An alias pointing to the specific version of the Amazon Lex bot to which this association is being made.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

name -> (string)

  

  The name of the association between the bot and the channel.

  

  

description -> (string)

  

  A description of the association between the bot and the channel.

  

  

botAlias -> (string)

  

  An alias pointing to the specific version of the Amazon Lex bot to which this association is being made.

  

  

botName -> (string)

  

  The name of the Amazon Lex bot.

  

  

createdDate -> (timestamp)

  

  The date that the association between the bot and the channel was created.

  

  

type -> (string)

  

  The type of the messaging platform.

  

  

botConfiguration -> (map)

  

  Provides information that the messaging platform needs to communicate with the Amazon Lex bot.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

