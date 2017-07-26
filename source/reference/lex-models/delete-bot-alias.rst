[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models delete-bot-alias:


****************
delete-bot-alias
****************



===========
Description
===========



Deletes an alias for the specified bot. 

 

You can't delete an alias that is used in the association between a bot and a messaging channel. If an alias is used in a channel association, the ``delete-bot`` operation returns a ``ResourceInUseException`` exception that includes a reference to the channel association that refers to the bot. You can remove the reference to the alias by deleting the channel association. If you get the same exception again, delete the referring association until the ``delete-bot-alias`` operation is successful.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/DeleteBotAlias>`_


========
Synopsis
========

::

    delete-bot-alias
  --name <value>
  --bot-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the alias to delete. The name is case sensitive. 

  

``--bot-name`` (string)


  The name of the bot that the alias points to.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None