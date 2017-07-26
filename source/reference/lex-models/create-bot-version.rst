[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models create-bot-version:


******************
create-bot-version
******************



===========
Description
===========



Creates a new version of the bot based on the ``$LATEST`` version. If the ``$LATEST`` version of this resource hasn't changed since you created the last version, Amazon Lex doesn't create a new version. It returns the last created version.

 

.. note::

   

  You can update only the ``$LATEST`` version of the bot. You can't update the numbered versions that you create with the ``create-bot-version`` operation.

   

 

When you create the first version of a bot, Amazon Lex sets the version to 1. Subsequent versions increment by 1. For more information, see  versioning-intro . 

 

This operation requires permission for the ``lex:CreateBotVersion`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/CreateBotVersion>`_


========
Synopsis
========

::

    create-bot-version
  --name <value>
  [--checksum <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the bot that you want to create a new version of. The name is case sensitive. 

  

``--checksum`` (string)


  Identifies a specific revision of the ``$LATEST`` version of the bot. If you specify a checksum and the ``$LATEST`` version of the bot has a different checksum, a ``PreconditionFailedException`` exception is returned and Amazon Lex doesn't publish a new version. If you don't specify a checksum, Amazon Lex publishes the ``$LATEST`` version.

  

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

  

  The message that Amazon Lex uses when it doesn't understand the user's request. For more information, see  put-bot . 

  

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

  

  When you send a request to create or update a bot, Amazon Lex sets the ``status`` response element to ``BUILDING`` . After Amazon Lex builds the bot, it sets ``status`` to ``READY`` . If Amazon Lex can't build the bot, it sets ``status`` to ``FAILED`` . Amazon Lex returns the reason for the failure in the ``failureReason`` response element. 

  

  

failureReason -> (string)

  

  If ``status`` is ``FAILED`` , Amazon Lex provides the reason that it failed to build the bot.

  

  

lastUpdatedDate -> (timestamp)

  

  The date when the ``$LATEST`` version of this bot was updated. 

  

  

createdDate -> (timestamp)

  

  The date when the bot version was created.

  

  

idleSessionTTLInSeconds -> (integer)

  

  The maximum time in seconds that Amazon Lex retains the data gathered in a conversation. For more information, see  put-bot .

  

  

voiceId -> (string)

  

  The Amazon Polly voice ID that Amazon Lex uses for voice interactions with the user.

  

  

checksum -> (string)

  

  Checksum identifying the version of the bot that was created.

  

  

version -> (string)

  

  The version of the bot. 

  

  

locale -> (string)

  

  Specifies the target locale for the bot. 

  

  

childDirected -> (boolean)

  

  For each Amazon Lex bot created with the Amazon Lex Model Building Service, you must specify whether your use of Amazon Lex is related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to the Children's Online Privacy Protection Act (COPPA) by specifying ``true`` or ``false`` in the ``childDirected`` field. By specifying ``true`` in the ``childDirected`` field, you confirm that your use of Amazon Lex **is** related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA. By specifying ``false`` in the ``childDirected`` field, you confirm that your use of Amazon Lex **is not** related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA. You may not specify a default value for the ``childDirected`` field that does not accurately reflect whether your use of Amazon Lex is related to a website, program, or other application that is directed or targeted, in whole or in part, to children under age 13 and subject to COPPA.

   

  If your use of Amazon Lex relates to a website, program, or other application that is directed in whole or in part, to children under age 13, you must obtain any required verifiable parental consent under COPPA. For information regarding the use of Amazon Lex in connection with websites, programs, or other applications that are directed or targeted, in whole or in part, to children under age 13, see the `Amazon Lex FAQ. <https://aws.amazon.com/lex/faqs#data-security>`_  

  

  

