[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-bot:


*******
get-bot
*******



===========
Description
===========



Returns metadata information for a specific bot. You must provide the bot name and the bot version or alias. 

 

The get-bot operation requires permissions for the ``lex:GetBot`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetBot>`_


========
Synopsis
========

::

    get-bot
  --name <value>
  --version-or-alias <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the bot. The name is case sensitive. 

  

``--version-or-alias`` (string)


  The version or alias of the bot.

  

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

  

  An array of ``intent`` objects. For more information, see  put-bot .

  

  (structure)

    

    Identifies the specific version of an intent.

    

    intentName -> (string)

      

      The name of the intent.

      

      

    intentVersion -> (string)

      

      The version of the intent.

      

      

    

  

clarificationPrompt -> (structure)

  

  The message Amazon Lex uses when it doesn't understand the user's request. For more information, see  put-bot . 

  

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

  

  The message that Amazon Lex returns when the user elects to end the conversation without completing it. For more information, see  put-bot .

  

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

  

  The status of the bot. If the bot is ready to run, the status is ``READY`` . If there was a problem with building the bot, the status is ``FAILED`` and the ``failureReason`` explains why the bot did not build. If the bot was saved but not built, the status is ``NOT BUILT`` .

  

  

failureReason -> (string)

  

  If ``status`` is ``FAILED`` , Amazon Lex explains why it failed to build the bot.

  

  

lastUpdatedDate -> (timestamp)

  

  The date that the bot was updated. When you create a resource, the creation date and last updated date are the same. 

  

  

createdDate -> (timestamp)

  

  The date that the bot was created.

  

  

idleSessionTTLInSeconds -> (integer)

  

  The maximum time in seconds that Amazon Lex retains the data gathered in a conversation. For more information, see  put-bot .

  

  

voiceId -> (string)

  

  The Amazon Polly voice ID that Amazon Lex uses for voice interaction with the user. For more information, see  put-bot .

  

  

checksum -> (string)

  

  Checksum of the bot used to identify a specific revision of the bot's ``$LATEST`` version.

  

  

version -> (string)

  

  The version of the bot. For a new bot, the version is always ``$LATEST`` .

  

  

locale -> (string)

  

  The target locale for the bot. 

  

  

childDirected -> (boolean)

  

  For each Amazon Lex bot created with the Amazon Lex Model Building Service, you must specify whether your use of Amazon Lex is related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to the Children's Online Privacy Protection Act (COPPA) by specifying ``true`` or ``false`` in the ``childDirected`` field. By specifying ``true`` in the ``childDirected`` field, you confirm that your use of Amazon Lex **is** related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA. By specifying ``false`` in the ``childDirected`` field, you confirm that your use of Amazon Lex **is not** related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA. You may not specify a default value for the ``childDirected`` field that does not accurately reflect whether your use of Amazon Lex is related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA.

   

  If your use of Amazon Lex relates to a website, program, or other application that is directed in whole or in part, to children under age 13, you must obtain any required verifiable parental consent under COPPA. For information regarding the use of Amazon Lex in connection with websites, programs, or other applications that are directed or targeted, in whole or in part, to children under age 13, see the `Amazon Lex FAQ. <https://aws.amazon.com/lex/faqs#data-security>`_  

  

  

