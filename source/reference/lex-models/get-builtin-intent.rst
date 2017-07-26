[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-builtin-intent:


******************
get-builtin-intent
******************



===========
Description
===========



Returns information about a built-in intent.

 

This operation requires permission for the ``lex:GetBuiltinIntent`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetBuiltinIntent>`_


========
Synopsis
========

::

    get-builtin-intent
  --signature <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--signature`` (string)


  The unique identifier for a built-in intent. To find the signature for an intent, see `Standard Built-in Intents <https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/built-in-intent-ref/standard-intents>`_ in the *Alexa Skills Kit* .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

signature -> (string)

  

  The unique identifier for a built-in intent.

  

  

supportedLocales -> (list)

  

  A list of locales that the intent supports.

  

  (string)

    

    

  

slots -> (list)

  

  An array of ``BuiltinIntentSlot`` objects, one entry for each slot type in the intent.

  

  (structure)

    

    Provides information about a slot used in a built-in intent.

    

    name -> (string)

      

      A list of the slots defined for the intent.

      

      

    

  

