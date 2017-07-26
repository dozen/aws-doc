[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models put-bot-alias:


*************
put-bot-alias
*************



===========
Description
===========



Creates an alias for the specified version of the bot or replaces an alias for the specified bot. To change the version of the bot that the alias points to, replace the alias. For more information about aliases, see  versioning-aliases .

 

This operation requires permissions for the ``lex:PutBotAlias`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/PutBotAlias>`_


========
Synopsis
========

::

    put-bot-alias
  --name <value>
  [--description <value>]
  --bot-version <value>
  --bot-name <value>
  [--checksum <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the alias. The name is *not* case sensitive.

  

``--description`` (string)


  A description of the alias.

  

``--bot-version`` (string)


  The version of the bot.

  

``--bot-name`` (string)


  The name of the bot.

  

``--checksum`` (string)


  Identifies a specific revision of the ``$LATEST`` version.

   

  When you create a new bot alias, leave the ``checksum`` field blank. If you specify a checksum you get a ``BadRequestException`` exception.

   

  When you want to update a bot alias, set the ``checksum`` field to the checksum of the most recent revision of the ``$LATEST`` version. If you don't specify the ``checksum`` field, or if the checksum does not match the ``$LATEST`` version, you get a ``PreconditionFailedException`` exception.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

name -> (string)

  

  The name of the alias.

  

  

description -> (string)

  

  A description of the alias.

  

  

botVersion -> (string)

  

  The version of the bot that the alias points to.

  

  

botName -> (string)

  

  The name of the bot that the alias points to.

  

  

lastUpdatedDate -> (timestamp)

  

  The date that the bot alias was updated. When you create a resource, the creation date and the last updated date are the same.

  

  

createdDate -> (timestamp)

  

  The date that the bot alias was created.

  

  

checksum -> (string)

  

  The checksum for the current version of the alias.

  

  

