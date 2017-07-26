[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-intent:


**********
get-intent
**********



===========
Description
===========



Returns information about an intent. In addition to the intent name, you must specify the intent version. 

 

This operation requires permissions to perform the ``lex:GetIntent`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetIntent>`_


========
Synopsis
========

::

    get-intent
  --name <value>
  --intent-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the intent. The name is case sensitive. 

  

``--intent-version`` (string)


  The version of the intent.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

name -> (string)

  

  The name of the intent.

  

  

description -> (string)

  

  A description of the intent.

  

  

slots -> (list)

  

  An array of intent slots configured for the intent.

  

  (structure)

    

    Identifies the version of a specific slot.

    

    name -> (string)

      

      The name of the slot.

      

      

    description -> (string)

      

      A description of the slot.

      

      

    slotConstraint -> (string)

      

      Specifies whether the slot is required or optional. 

      

      

    slotType -> (string)

      

      The type of the slot, either a custom slot type that you defined or one of the built-in slot types.

      

      

    slotTypeVersion -> (string)

      

      The version of the slot type.

      

      

    valueElicitationPrompt -> (structure)

      

      The prompt that Amazon Lex uses to elicit the slot value from the user.

      

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

        

        

      

    priority -> (integer)

      

      Directs Lex the order in which to elicit this slot value from the user. For example, if the intent has two slots with priorities 1 and 2, AWS Lex first elicits a value for the slot with priority 1.

       

      If multiple slots share the same priority, the order in which Lex elicits values is arbitrary.

      

      

    sampleUtterances -> (list)

      

      If you know a specific pattern with which users might respond to an Amazon Lex request for a slot value, you can provide those utterances to improve accuracy. This is optional. In most cases, Amazon Lex is capable of understanding user utterances. 

      

      (string)

        

        

      

    responseCard -> (string)

      

      A set of possible responses for the slot type used by text-based clients. A user chooses an option from the response card, instead of using text to reply. 

      

      

    

  

sampleUtterances -> (list)

  

  An array of sample utterances configured for the intent.

  

  (string)

    

    

  

confirmationPrompt -> (structure)

  

  If defined in the bot, Amazon Lex uses prompt to confirm the intent before fulfilling the user's request. For more information, see  put-intent . 

  

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

    

    

  

rejectionStatement -> (structure)

  

  If the user answers "no" to the question defined in ``confirmationPrompt`` , Amazon Lex responds with this statement to acknowledge that the intent was canceled. 

  

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

    

    

  

followUpPrompt -> (structure)

  

  If defined in the bot, Amazon Lex uses this prompt to solicit additional user activity after the intent is fulfilled. For more information, see  put-intent .

  

  prompt -> (structure)

    

    Prompts for information from the user. 

    

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

      

      

    

  rejectionStatement -> (structure)

    

    If the user answers "no" to the question defined in the ``prompt`` field, Amazon Lex responds with this statement to acknowledge that the intent was canceled. 

    

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

      

      

    

  

conclusionStatement -> (structure)

  

  After the Lambda function specified in the ``fulfillmentActivity`` element fulfills the intent, Amazon Lex conveys this statement to the user.

  

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

    

    

  

dialogCodeHook -> (structure)

  

  If defined in the bot, Amazon Amazon Lex invokes this Lambda function for each user input. For more information, see  put-intent . 

  

  uri -> (string)

    

    The Amazon Resource Name (ARN) of the Lambda function.

    

    

  messageVersion -> (string)

    

    The version of the request-response that you want Amazon Lex to use to invoke your Lambda function. For more information, see  using-lambda .

    

    

  

fulfillmentActivity -> (structure)

  

  Describes how the intent is fulfilled. For more information, see  put-intent . 

  

  type -> (string)

    

    How the intent should be fulfilled, either by running a Lambda function or by returning the slot data to the client application. 

    

    

  codeHook -> (structure)

    

    A description of the Lambda function that is run to fulfill the intent. 

    

    uri -> (string)

      

      The Amazon Resource Name (ARN) of the Lambda function.

      

      

    messageVersion -> (string)

      

      The version of the request-response that you want Amazon Lex to use to invoke your Lambda function. For more information, see  using-lambda .

      

      

    

  

parentIntentSignature -> (string)

  

  A unique identifier for a built-in intent.

  

  

lastUpdatedDate -> (timestamp)

  

  The date that the intent was updated. When you create a resource, the creation date and the last updated date are the same. 

  

  

createdDate -> (timestamp)

  

  The date that the intent was created.

  

  

version -> (string)

  

  The version of the intent.

  

  

checksum -> (string)

  

  Checksum of the intent.

  

  

