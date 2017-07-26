[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models delete-bot:


**********
delete-bot
**********



===========
Description
===========



Deletes all versions of the bot, including the ``$LATEST`` version. To delete a specific version of the bot, use the  delete-bot-version operation.

 

If a bot has an alias, you can't delete it. Instead, the ``delete-bot`` operation returns a ``ResourceInUseException`` exception that includes a reference to the alias that refers to the bot. To remove the reference to the bot, delete the alias. If you get the same exception again, delete the referring alias until the ``delete-bot`` operation is successful.

 

This operation requires permissions for the ``lex:DeleteBot`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/DeleteBot>`_


========
Synopsis
========

::

    delete-bot
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the bot. The name is case sensitive. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None