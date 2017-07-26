[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-bots:


********
get-bots
********



===========
Description
===========



Returns bot information as follows: 

 

 
* If you provide the ``nameContains`` field, the response includes information for the ``$LATEST`` version of all bots whose name contains the specified string. 
 
* If you don't specify the ``nameContains`` field, the operation returns information about the ``$LATEST`` version of all of your bots. 
 

 

This operation requires permission for the ``lex:GetBots`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetBots>`_


========
Synopsis
========

::

    get-bots
  [--next-token <value>]
  [--max-results <value>]
  [--name-contains <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  A pagination token that fetches the next page of bots. If the response to this call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of bots, specify the pagination token in the next request. 

  

``--max-results`` (integer)


  The maximum number of bots to return in the response that the request will return. The default is 10.

  

``--name-contains`` (string)


  Substring to match in bot names. A bot will be returned if any part of its name matches the substring. For example, "xyz" matches both "xyzabc" and "abcxyz."

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

bots -> (list)

  

  An array of ``botMetadata`` objects, with one entry for each bot. 

  

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

  

  If the response is truncated, it includes a pagination token that you can specify in your next request to fetch the next page of bots. 

  

  

