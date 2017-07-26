[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-builtin-slot-types:


**********************
get-builtin-slot-types
**********************



===========
Description
===========



Gets a list of built-in slot types that meet the specified criteria.

 

For a list of built-in slot types, see `Slot Type Reference <https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/built-in-intent-ref/slot-type-reference>`_ in the *Alexa Skills Kit* .

 

This operation requires permission for the ``lex:GetBuiltInSlotTypes`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetBuiltinSlotTypes>`_


========
Synopsis
========

::

    get-builtin-slot-types
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


  A list of locales that the slot type supports.

  

  Possible values:

  
  *   ``en-US``

  

  

``--signature-contains`` (string)


  Substring to match in built-in slot type signatures. A slot type will be returned if any part of its signature matches the substring. For example, "xyz" matches both "xyzabc" and "abcxyz."

  

``--next-token`` (string)


  A pagination token that fetches the next page of slot types. If the response to this API call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of slot types, specify the pagination token in the next request.

  

``--max-results`` (integer)


  The maximum number of slot types to return in the response. The default is 10.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

slotTypes -> (list)

  

  An array of ``BuiltInSlotTypeMetadata`` objects, one entry for each slot type returned.

  

  (structure)

    

    Provides information about a built in slot type.

    

    signature -> (string)

      

      A unique identifier for the built-in slot type. To find the signature for a slot type, see `Slot Type Reference <https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/built-in-intent-ref/slot-type-reference>`_ in the *Alexa Skills Kit* .

      

      

    supportedLocales -> (list)

      

      A list of target locales for the slot. 

      

      (string)

        

        

      

    

  

nextToken -> (string)

  

  If the response is truncated, the response includes a pagination token that you can use in your next request to fetch the next page of slot types.

  

  

