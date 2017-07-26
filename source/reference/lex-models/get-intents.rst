[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-intents:


***********
get-intents
***********



===========
Description
===========



Returns intent information as follows: 

 

 
* If you specify the ``nameContains`` field, returns the ``$LATEST`` version of all intents that contain the specified string. 
 
* If you don't specify the ``nameContains`` field, returns information about the ``$LATEST`` version of all intents.  
 

 

The operation requires permission for the ``lex:GetIntents`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetIntents>`_


========
Synopsis
========

::

    get-intents
  [--next-token <value>]
  [--max-results <value>]
  [--name-contains <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  A pagination token that fetches the next page of intents. If the response to this API call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of intents, specify the pagination token in the next request. 

  

``--max-results`` (integer)


  The maximum number of intents to return in the response. The default is 10.

  

``--name-contains`` (string)


  Substring to match in intent names. An intent will be returned if any part of its name matches the substring. For example, "xyz" matches both "xyzabc" and "abcxyz."

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

intents -> (list)

  

  An array of ``Intent`` objects. For more information, see  put-bot .

  

  (structure)

    

    Provides information about an intent.

    

    name -> (string)

      

      The name of the intent.

      

      

    description -> (string)

      

      A description of the intent.

      

      

    lastUpdatedDate -> (timestamp)

      

      The date that the intent was updated. When you create an intent, the creation date and last updated date are the same.

      

      

    createdDate -> (timestamp)

      

      The date that the intent was created.

      

      

    version -> (string)

      

      The version of the intent.

      

      

    

  

nextToken -> (string)

  

  If the response is truncated, the response includes a pagination token that you can specify in your next request to fetch the next page of intents. 

  

  

