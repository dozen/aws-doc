[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-builtin-intents:


*******************
get-builtin-intents
*******************



===========
Description
===========



Gets a list of built-in intents that meet the specified criteria.

 

This operation requires permission for the ``lex:GetBuiltinIntents`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetBuiltinIntents>`_


========
Synopsis
========

::

    get-builtin-intents
  [--locale <value>]
  [--signature-contains <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--locale`` (string)


  A list of locales that the intent supports.

  

  Possible values:

  
  *   ``en-US``

  

  

``--signature-contains`` (string)


  Substring to match in built-in intent signatures. An intent will be returned if any part of its signature matches the substring. For example, "xyz" matches both "xyzabc" and "abcxyz." To find the signature for an intent, see `Standard Built-in Intents <https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/built-in-intent-ref/standard-intents>`_ in the *Alexa Skills Kit* .

  

``--next-token`` (string)


  A pagination token that fetches the next page of intents. If this API call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of intents, use the pagination token in the next request.

  

``--max-results`` (integer)


  The maximum number of intents to return in the response. The default is 10.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

intents -> (list)

  

  An array of ``builtinIntentMetadata`` objects, one for each intent in the response.

  

  (structure)

    

    Provides metadata for a built-in intent.

    

    signature -> (string)

      

      A unique identifier for the built-in intent. To find the signature for an intent, see `Standard Built-in Intents <https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/built-in-intent-ref/standard-intents>`_ in the *Alexa Skills Kit* .

      

      

    supportedLocales -> (list)

      

      A list of identifiers for the locales that the intent supports.

      

      (string)

        

        

      

    

  

nextToken -> (string)

  

  A pagination token that fetches the next page of intents. If the response to this API call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of intents, specify the pagination token in the next request.

  

  

