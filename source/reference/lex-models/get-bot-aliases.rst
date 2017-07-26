[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-bot-aliases:


***************
get-bot-aliases
***************



===========
Description
===========



Returns a list of aliases for a specified Amazon Lex bot.

 

This operation requires permissions for the ``lex:GetBotAliases`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetBotAliases>`_


========
Synopsis
========

::

    get-bot-aliases
  --bot-name <value>
  [--next-token <value>]
  [--max-results <value>]
  [--name-contains <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bot-name`` (string)


  The name of the bot.

  

``--next-token`` (string)


  A pagination token for fetching the next page of aliases. If the response to this call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of aliases, specify the pagination token in the next request. 

  

``--max-results`` (integer)


  The maximum number of aliases to return in the response. The default is 50. . 

  

``--name-contains`` (string)


  Substring to match in bot alias names. An alias will be returned if any part of its name matches the substring. For example, "xyz" matches both "xyzabc" and "abcxyz."

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

BotAliases -> (list)

  

  An array of ``BotAliasMetadata`` objects, each describing a bot alias.

  

  (structure)

    

    Provides information about a bot alias.

    

    name -> (string)

      

      The name of the bot alias.

      

      

    description -> (string)

      

      A description of the bot alias.

      

      

    botVersion -> (string)

      

      The version of the Amazon Lex bot to which the alias points.

      

      

    botName -> (string)

      

      The name of the bot to which the alias points.

      

      

    lastUpdatedDate -> (timestamp)

      

      The date that the bot alias was updated. When you create a resource, the creation date and last updated date are the same.

      

      

    createdDate -> (timestamp)

      

      The date that the bot alias was created.

      

      

    checksum -> (string)

      

      Checksum of the bot alias.

      

      

    

  

nextToken -> (string)

  

  A pagination token for fetching next page of aliases. If the response to this call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of aliases, specify the pagination token in the next request. 

  

  

