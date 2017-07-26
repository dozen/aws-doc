[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models delete-bot-channel-association:


******************************
delete-bot-channel-association
******************************



===========
Description
===========



Deletes the association between an Amazon Lex bot and a messaging platform.

 

This operation requires permission for the ``lex:DeleteBotChannelAssociation`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/DeleteBotChannelAssociation>`_


========
Synopsis
========

::

    delete-bot-channel-association
  --name <value>
  --bot-name <value>
  --bot-alias <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the association. The name is case sensitive. 

  

``--bot-name`` (string)


  The name of the Amazon Lex bot.

  

``--bot-alias`` (string)


  An alias that points to the specific version of the Amazon Lex bot to which this association is being made.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None