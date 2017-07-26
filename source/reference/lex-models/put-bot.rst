[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models put-bot:


*******
put-bot
*******



===========
Description
===========



Creates an Amazon Lex conversational bot or replaces an existing bot. When you create or update a bot you are only required to specify a name. You can use this to add intents later, or to remove intents from an existing bot. When you create a bot with a name only, the bot is created or updated but Amazon Lex returns the ```` response ``FAILED`` . You can build the bot after you add one or more intents. For more information about Amazon Lex bots, see  how-it-works . 

 

If you specify the name of an existing bot, the fields in the request replace the existing values in the ``$LATEST`` version of the bot. Amazon Lex removes any fields that you don't provide values for in the request, except for the ``idleTTLInSeconds`` and ``privacySettings`` fields, which are set to their default values. If you don't specify values for required fields, Amazon Lex throws an exception.

 

This operation requires permissions for the ``lex:PutBot`` action. For more information, see  auth-and-access-control .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/PutBot>`_


========
Synopsis
========

::

    put-bot
  --name <value>
  [--description <value>]
  [--intents <value>]
  [--clarification-prompt <value>]
  [--abort-statement <value>]
  [--idle-session-ttl-in-seconds <value>]
  [--voice-id <value>]
  [--checksum <value>]
  [--process-behavior <value>]
  --locale <value>
  --child-directed | --no-child-directed
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the bot. The name is *not* case sensitive. 

  

``--description`` (string)


  A description of the bot.

  

``--intents`` (list)


  An array of ``Intent`` objects. Each intent represents a command that a user can express. For example, a pizza ordering bot might support an OrderPizza intent. For more information, see  how-it-works .

  



Shorthand Syntax::

    intentName=string,intentVersion=string ...




JSON Syntax::

  [
    {
      "intentName": "string",
      "intentVersion": "string"
    }
    ...
  ]



``--clarification-prompt`` (structure)


  When Amazon Lex doesn't understand the user's intent, it uses this message to get clarification. To specify how many times Amazon Lex should repeate the clarification prompt, use the ``maxAttempts`` field. If Amazon Lex still doesn't understand, it sends the message in the ``abortStatement`` field. 

   

  When you create a clarification prompt, make sure that it suggests the correct response from the user. for example, for a bot that orders pizza and drinks, you might create this clarification prompt: "What would you like to do? You can say 'Order a pizza' or 'Order a drink.'"

  



Shorthand Syntax::

    messages=[{contentType=string,content=string},{contentType=string,content=string}],maxAttempts=integer,responseCard=string




JSON Syntax::

  {
    "messages": [
      {
        "contentType": "PlainText"|"SSML",
        "content": "string"
      }
      ...
    ],
    "maxAttempts": integer,
    "responseCard": "string"
  }



``--abort-statement`` (structure)


  When Amazon Lex can't understand the user's input in context, it tries to elicit the information a few times. After that, Amazon Lex sends the message defined in ``abortStatement`` to the user, and then aborts the conversation. To set the number of retries, use the ``valueElicitationPrompt`` field for the slot type. 

   

  For example, in a pizza ordering bot, Amazon Lex might ask a user "What type of crust would you like?" If the user's response is not one of the expected responses (for example, "thin crust, "deep dish," etc.), Amazon Lex tries to elicit a correct response a few more times. 

   

  For example, in a pizza ordering application, ``OrderPizza`` might be one of the intents. This intent might require the ``CrustType`` slot. You specify the ``valueElicitationPrompt`` field when you create the ``CrustType`` slot.

  



Shorthand Syntax::

    messages=[{contentType=string,content=string},{contentType=string,content=string}],responseCard=string




JSON Syntax::

  {
    "messages": [
      {
        "contentType": "PlainText"|"SSML",
        "content": "string"
      }
      ...
    ],
    "responseCard": "string"
  }



``--idle-session-ttl-in-seconds`` (integer)


  The maximum time in seconds that Amazon Lex retains the data gathered in a conversation.

   

  A user interaction session remains active for the amount of time specified. If no conversation occurs during this time, the session expires and Amazon Lex deletes any data provided before the timeout.

   

  For example, suppose that a user chooses the OrderPizza intent, but gets sidetracked halfway through placing an order. If the user doesn't complete the order within the specified time, Amazon Lex discards the slot information that it gathered, and the user must start over.

   

  If you don't include the ``idleSessionTTLInSeconds`` element in a ``put-bot`` operation request, Amazon Lex uses the default value. This is also true if the request replaces an existing bot.

   

  The default is 300 seconds (5 minutes).

  

``--voice-id`` (string)


  The Amazon Polly voice ID that you want Amazon Lex to use for voice interactions with the user. The locale configured for the voice must match the locale of the bot. For more information, see `Available Voices <http://docs.aws.amazon.com/polly/latest/dg/voicelist.html>`_ in the *Amazon Polly Developer Guide* .

  

``--checksum`` (string)


  Identifies a specific revision of the ``$LATEST`` version.

   

  When you create a new bot, leave the ``checksum`` field blank. If you specify a checksum you get a ``BadRequestException`` exception.

   

  When you want to update a bot, set the ``checksum`` field to the checksum of the most recent revision of the ``$LATEST`` version. If you don't specify the ``checksum`` field, or if the checksum does not match the ``$LATEST`` version, you get a ``PreconditionFailedException`` exception.

  

``--process-behavior`` (string)


  If you set the ``processBehavior`` element to ``Build`` , Amazon Lex builds the bot so that it can be run. If you set the element to ``Save`` Amazon Lex saves the bot, but doesn't build it. 

   

  If you don't specify this value, the default value is ``Save`` .

  

  Possible values:

  
  *   ``SAVE``

  
  *   ``BUILD``

  

  

``--locale`` (string)


  Specifies the target locale for the bot. Any intent used in the bot must be compatible with the locale of the bot. 

   

  The default is ``en-US`` .

  

  Possible values:

  
  *   ``en-US``

  

  

``--child-directed`` | ``--no-child-directed`` (boolean)


  For each Amazon Lex bot created with the Amazon Lex Model Building Service, you must specify whether your use of Amazon Lex is related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to the Children's Online Privacy Protection Act (COPPA) by specifying ``true`` or ``false`` in the ``childDirected`` field. By specifying ``true`` in the ``childDirected`` field, you confirm that your use of Amazon Lex **is** related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA. By specifying ``false`` in the ``childDirected`` field, you confirm that your use of Amazon Lex **is not** related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA. You may not specify a default value for the ``childDirected`` field that does not accurately reflect whether your use of Amazon Lex is related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA.

   

  If your use of Amazon Lex relates to a website, program, or other application that is directed in whole or in part, to children under age 13, you must obtain any required verifiable parental consent under COPPA. For information regarding the use of Amazon Lex in connection with websites, programs, or other applications that are directed or targeted, in whole or in part, to children under age 13, see the `Amazon Lex FAQ. <https://aws.amazon.com/lex/faqs#data-security>`_  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

name -> (string)

  

  The name of the bot.

  

  

description -> (string)

  

  A description of the bot.

  

  

intents -> (list)

  

  An array of ``Intent`` objects. For more information, see  put-bot .

  

  (structure)

    

    Identifies the specific version of an intent.

    

    intentName -> (string)

      

      The name of the intent.

      

      

    intentVersion -> (string)

      

      The version of the intent.

      

      

    

  

clarificationPrompt -> (structure)

  

  The prompts that Amazon Lex uses when it doesn't understand the user's intent. For more information, see  put-bot . 

  

  messages -> (list)

    

    An array of objects, each of which provides a message string and its type. You can specify the message string in plain text or in Speech Synthesis Markup Language (SSML).

    

    (structure)

      

      The message object that provides the message text and its type.

      

      contentType -> (string)

        

        The content type of the message string.

        

        

      content -> (string)

        

        The text of the message.

        

        

      

    

  maxAttempts -> (integer)

    

    The number of times to prompt the user for information.

    

    

  responseCard -> (string)

    

    A response card. Amazon Lex uses this prompt at runtime, in the ``PostText`` API response. It substitutes session attributes and slot values for placeholders in the response card. For more information, see  ex-resp-card . 

    

    

  

abortStatement -> (structure)

  

  The message that Amazon Lex uses to abort a conversation. For more information, see  put-bot .

  

  messages -> (list)

    

    A collection of message objects.

    

    (structure)

      

      The message object that provides the message text and its type.

      

      contentType -> (string)

        

        The content type of the message string.

        

        

      content -> (string)

        

        The text of the message.

        

        

      

    

  responseCard -> (string)

    

    At runtime, if the client is using the `PostText <http://docs.aws.amazon.com/lex/latest/dg/API_runtime_PostText.html>`_ API, Amazon Lex includes the response card in the response. It substitutes all of the session attributes and slot values for placeholders in the response card. 

    

    

  

status -> (string)

  

  When you send a request to create a bot with ``processBehavior`` set to ``BUILD`` , Amazon Lex sets the ``status`` response element to ``BUILDING`` . After Amazon Lex builds the bot, it sets ``status`` to ``READY`` . If Amazon Lex can't build the bot, Amazon Lex sets ``status`` to ``FAILED`` . Amazon Lex returns the reason for the failure in the ``failureReason`` response element. 

   

  When you set ``processBehavior`` to ``SAVE`` , Amazon Lex sets the status code to ``NOT BUILT`` .

  

  

failureReason -> (string)

  

  If ``status`` is ``FAILED`` , Amazon Lex provides the reason that it failed to build the bot.

  

  

lastUpdatedDate -> (timestamp)

  

  The date that the bot was updated. When you create a resource, the creation date and last updated date are the same.

  

  

createdDate -> (timestamp)

  

  The date that the bot was created.

  

  

idleSessionTTLInSeconds -> (integer)

  

  The maximum length of time that Amazon Lex retains the data gathered in a conversation. For more information, see  put-bot .

  

  

voiceId -> (string)

  

  The Amazon Polly voice ID that Amazon Lex uses for voice interaction with the user. For more information, see  put-bot .

  

  

checksum -> (string)

  

  Checksum of the bot that you created.

  

  

version -> (string)

  

  The version of the bot. For a new bot, the version is always ``$LATEST`` .

  

  

locale -> (string)

  

  The target locale for the bot. 

  

  

childDirected -> (boolean)

  

  For each Amazon Lex bot created with the Amazon Lex Model Building Service, you must specify whether your use of Amazon Lex is related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to the Children's Online Privacy Protection Act (COPPA) by specifying ``true`` or ``false`` in the ``childDirected`` field. By specifying ``true`` in the ``childDirected`` field, you confirm that your use of Amazon Lex **is** related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA. By specifying ``false`` in the ``childDirected`` field, you confirm that your use of Amazon Lex **is not** related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA. You may not specify a default value for the ``childDirected`` field that does not accurately reflect whether your use of Amazon Lex is related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA.

   

  If your use of Amazon Lex relates to a website, program, or other application that is directed in whole or in part, to children under age 13, you must obtain any required verifiable parental consent under COPPA. For information regarding the use of Amazon Lex in connection with websites, programs, or other applications that are directed or targeted, in whole or in part, to children under age 13, see the `Amazon Lex FAQ. <https://aws.amazon.com/lex/faqs#data-security>`_  

  

  

