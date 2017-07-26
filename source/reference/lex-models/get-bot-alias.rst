[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-bot-alias:


*************
get-bot-alias
*************



===========
Description
===========



Returns information about an Amazon Lex bot alias. For more information about aliases, see  versioning-aliases .

 

This operation requires permissions for the ``lex:GetBotAlias`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetBotAlias>`_


========
Synopsis
========

::

    get-bot-alias
  --name <value>
  --bot-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the bot alias. The name is case sensitive.

  

``--bot-name`` (string)


  The name of the bot.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

name -> (string)

  

  The name of the bot alias.

  

  

description -> (string)

  

  A description of the bot alias.

  

  

botVersion -> (string)

  

  The version of the bot that the alias points to.

  

  

botName -> (string)

  

  The name of the bot that the alias points to.

  

  

lastUpdatedDate -> (timestamp)

  

  The date that the bot alias was updated. When you create a resource, the creation date and the last updated date are the same.

  

  

createdDate -> (timestamp)

  

  The date that the bot alias was created.

  

  

checksum -> (string)

  

  Checksum of the bot alias.

  

  

