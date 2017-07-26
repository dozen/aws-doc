[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-bot-versions:


****************
get-bot-versions
****************



===========
Description
===========



Gets information about all of the versions of a bot.

 

The ``get-bot-versions`` operation returns a ``BotMetadata`` object for each version of a bot. For example, if a bot has three numbered versions, the ``get-bot-versions`` operation returns four ``BotMetadata`` objects in the response, one for each numbered version and one for the ``$LATEST`` version. 

 

The ``get-bot-versions`` operation always returns at least one version, the ``$LATEST`` version.

 

This operation requires permissions for the ``lex:GetBotVersions`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetBotVersions>`_


========
Synopsis
========

::

    get-bot-versions
  --name <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the bot for which versions should be returned.

  

``--next-token`` (string)


  A pagination token for fetching the next page of bot versions. If the response to this call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of versions, specify the pagination token in the next request. 

  

``--max-results`` (integer)


  The maximum number of bot versions to return in the response. The default is 10.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

bots -> (list)

  

  An array of ``BotMetadata`` objects, one for each numbered version of the bot plus one for the ``$LATEST`` version.

  

  (structure)

    

    Provides information about a bot. .

    

    name -> (string)

      

      The name of the bot. 

      

      

    description -> (string)

      

      A description of the bot.

      

      

    status -> (string)

      

      The status of the bot.

      

      

    lastUpdatedDate -> (timestamp)

      

      The date that the bot was updated. When you create a bot, the creation date and last updated date are the same. 

      

      

    createdDate -> (timestamp)

      

      The date that the bot was created.

      

      

    version -> (string)

      

      The version of the bot. For a new bot, the version is always ``$LATEST`` .

      

      

    

  

nextToken -> (string)

  

  A pagination token for fetching the next page of bot versions. If the response to this call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of versions, specify the pagination token in the next request. 

  

  

