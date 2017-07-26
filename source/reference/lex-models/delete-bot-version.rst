[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models delete-bot-version:


******************
delete-bot-version
******************



===========
Description
===========



Deletes a specific version of a bot. To delete all versions of a bot, use the  delete-bot operation. 

 

This operation requires permissions for the ``lex:DeleteBotVersion`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/DeleteBotVersion>`_


========
Synopsis
========

::

    delete-bot-version
  --name <value>
  --bot-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the bot.

  

``--bot-version`` (string)


  The version of the bot to delete. You cannot delete the ``$LATEST`` version of the bot. To delete the ``$LATEST`` version, use the  delete-bot operation.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None