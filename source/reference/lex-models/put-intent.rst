[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models put-intent:


**********
put-intent
**********



===========
Description
===========



Creates an intent or replaces an existing intent.

 

To define the interaction between the user and your bot, you use one or more intents. For a pizza ordering bot, for example, you would create an ``OrderPizza`` intent. 

 

To create an intent or replace an existing intent, you must provide the following:

 

 
* Intent name. For example, ``OrderPizza`` . 
 
* Sample utterances. For example, "Can I order a pizza, please." and "I want to order a pizza." 
 
* Information to be gathered. You specify slot types for the information that your bot will request from the user. You can specify standard slot types, such as a date or a time, or custom slot types such as the size and crust of a pizza. 
 
* How the intent will be fulfilled. You can provide a Lambda function or configure the intent to return the intent information to the client application. If you use a Lambda function, when all of the intent information is available, Amazon Lex invokes your Lambda function. If you configure your intent to return the intent information to the client application.  
 

 

You can specify other optional information in the request, such as:

 

 
* A confirmation prompt to ask the user to confirm an intent. For example, "Shall I order your pizza?" 
 
* A conclusion statement to send to the user after the intent has been fulfilled. For example, "I placed your pizza order." 
 
* A follow-up prompt that asks the user for additional activity. For example, asking "Do you want to order a drink with your pizza?" 
 

 

If you specify an existing intent name to update the intent, Amazon Lex replaces the values in the ``$LATEST`` version of the slot type with the values in the request. Amazon Lex removes fields that you don't provide in the request. If you don't specify the required fields, Amazon Lex throws an exception.

 

For more information, see  how-it-works .

 

This operation requires permissions for the ``lex:PutIntent`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/PutIntent>`_


========
Synopsis
========

::

    put-intent
  --name <value>
  [--description <value>]
  [--slots <value>]
  [--sample-utterances <value>]
  [--confirmation-prompt <value>]
  [--rejection-statement <value>]
  [--follow-up-prompt <value>]
  [--conclusion-statement <value>]
  [--dialog-code-hook <value>]
  [--fulfillment-activity <value>]
  [--parent-intent-signature <value>]
  [--checksum <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the intent. The name is *not* case sensitive. 

   

  The name can't match a built-in intent name, or a built-in intent name with "AMAZON." removed. For example, because there is a built-in intent called ``AMAZON.HelpIntent`` , you can't create a custom intent called ``HelpIntent`` .

   

  For a list of built-in intents, see `Standard Built-in Intents <https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/built-in-intent-ref/standard-intents>`_ in the *Alexa Skills Kit* .

  

``--description`` (string)


  A description of the intent.

  

``--slots`` (list)


  An array of intent slots. At runtime, Amazon Lex elicits required slot values from the user using prompts defined in the slots. For more information, see xref linkend="how-it-works"/. 

  



JSON Syntax::

  [
    {
      "name": "string",
      "description": "string",
      "slotConstraint": "Required"|"Optional",
      "slotType": "string",
      "slotTypeVersion": "string",
      "valueElicitationPrompt": {
        "messages": [
          {
            "contentType": "PlainText"|"SSML",
            "content": "string"
          }
          ...
        ],
        "maxAttempts": integer,
        "responseCard": "string"
      },
      "priority": integer,
      "sampleUtterances": ["string", ...],
      "responseCard": "string"
    }
    ...
  ]



``--sample-utterances`` (list)


  An array of utterances (strings) that a user might say to signal the intent. For example, "I want {PizzaSize} pizza", "Order {Quantity} {PizzaSize} pizzas". 

   

  In each utterance, a slot name is enclosed in curly braces. 

  



Syntax::

  "string" "string" ...



``--confirmation-prompt`` (structure)


  Prompts the user to confirm the intent. This question should have a yes or no answer.

   

  Amazon Lex uses this prompt to ensure that the user acknowledges that the intent is ready for fulfillment. For example, with the ``OrderPizza`` intent, you might want to confirm that the order is correct before placing it. For other intents, such as intents that simply respond to user questions, you might not need to ask the user for confirmation before providing the information. 

   

  .. note::

     

    You you must provide both the ``rejectionStatement`` and the ``confirmationPrompt`` , or neither.

     

  



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



``--rejection-statement`` (structure)


  When the user answers "no" to the question defined in ``confirmationPrompt`` , Amazon Lex responds with this statement to acknowledge that the intent was canceled. 

   

  .. note::

     

    You must provide both the ``rejectionStatement`` and the ``confirmationPrompt`` , or neither.

     

  



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



``--follow-up-prompt`` (structure)


  Amazon Lex uses this prompt to solicit additional activity after fulfilling an intent. For example, after the ``OrderPizza`` intent is fulfilled, you might prompt the user to order a drink.

   

  The action that Amazon Lex takes depends on the user's response, as follows:

   

   
  * If the user says "Yes" it responds with the clarification prompt that is configured for the bot. 
   
  * if the user says "Yes" and continues with an utterance that triggers an intent it starts a conversation for the intent. 
   
  * If the user says "No" it responds with the rejection statement configured for the the follow-up prompt. 
   
  * If it doesn't recognize the utterance it repeats the follow-up prompt again. 
   

   

  The ``followUpPrompt`` field and the ``conclusionStatement`` field are mutually exclusive. You can specify only one. 

  



JSON Syntax::

  {
    "prompt": {
      "messages": [
        {
          "contentType": "PlainText"|"SSML",
          "content": "string"
        }
        ...
      ],
      "maxAttempts": integer,
      "responseCard": "string"
    },
    "rejectionStatement": {
      "messages": [
        {
          "contentType": "PlainText"|"SSML",
          "content": "string"
        }
        ...
      ],
      "responseCard": "string"
    }
  }



``--conclusion-statement`` (structure)


  The statement that you want Amazon Lex to convey to the user after the intent is successfully fulfilled by the Lambda function. 

   

  This element is relevant only if you provide a Lambda function in the ``fulfillmentActivity`` . If you return the intent to the client application, you can't specify this element.

   

  .. note::

     

    The ``followUpPrompt`` and ``conclusionStatement`` are mutually exclusive. You can specify only one.

     

  



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



``--dialog-code-hook`` (structure)


  Specifies a Lambda function to invoke for each user input. You can invoke this Lambda function to personalize user interaction. 

   

  For example, suppose your bot determines that the user is John. Your Lambda function might retrieve John's information from a backend database and prepopulate some of the values. For example, if you find that John is gluten intolerant, you might set the corresponding intent slot, ``GlutenIntolerant`` , to true. You might find John's phone number and set the corresponding session attribute. 

  



Shorthand Syntax::

    uri=string,messageVersion=string




JSON Syntax::

  {
    "uri": "string",
    "messageVersion": "string"
  }



``--fulfillment-activity`` (structure)


  Describes how the intent is fulfilled. For example, after a user provides all of the information for a pizza order, ``fulfillmentActivity`` defines how the bot places an order with a local pizza store. 

   

  You might configure Amazon Lex to return all of the intent information to the client application, or direct it to invoke a Lambda function that can process the intent (for example, place an order with a pizzeria). 

  



Shorthand Syntax::

    type=string,codeHook={uri=string,messageVersion=string}




JSON Syntax::

  {
    "type": "ReturnIntent"|"CodeHook",
    "codeHook": {
      "uri": "string",
      "messageVersion": "string"
    }
  }



``--parent-intent-signature`` (string)


  A unique identifier for the built-in intent to base this intent on. To find the signature for an intent, see `Standard Built-in Intents <https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/built-in-intent-ref/standard-intents>`_ in the *Alexa Skills Kit* .

  

``--checksum`` (string)


  Identifies a specific revision of the ``$LATEST`` version.

   

  When you create a new intent, leave the ``checksum`` field blank. If you specify a checksum you get a ``BadRequestException`` exception.

   

  When you want to update a intent, set the ``checksum`` field to the checksum of the most recent revision of the ``$LATEST`` version. If you don't specify the ``checksum`` field, or if the checksum does not match the ``$LATEST`` version, you get a ``PreconditionFailedException`` exception.

  

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

  

  An array of intent slots that are configured for the intent.

  

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

  

  An array of sample utterances that are configured for the intent. 

  

  (string)

    

    

  

confirmationPrompt -> (structure)

  

  If defined in the intent, Amazon Lex prompts the user to confirm the intent before fulfilling it.

  

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

  

  If the user answers "no" to the question defined in ``confirmationPrompt`` Amazon Lex responds with this statement to acknowledge that the intent was canceled. 

  

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

  

  If defined in the intent, Amazon Lex uses this prompt to solicit additional user activity after the intent is fulfilled.

  

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

  

  After the Lambda function specified in the``fulfillmentActivity`` intent fulfills the intent, Amazon Lex conveys this statement to the user.

  

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

  

  If defined in the intent, Amazon Lex invokes this Lambda function for each user input.

  

  uri -> (string)

    

    The Amazon Resource Name (ARN) of the Lambda function.

    

    

  messageVersion -> (string)

    

    The version of the request-response that you want Amazon Lex to use to invoke your Lambda function. For more information, see  using-lambda .

    

    

  

fulfillmentActivity -> (structure)

  

  If defined in the intent, Amazon Lex invokes this Lambda function to fulfill the intent after the user provides all of the information required by the intent.

  

  type -> (string)

    

    How the intent should be fulfilled, either by running a Lambda function or by returning the slot data to the client application. 

    

    

  codeHook -> (structure)

    

    A description of the Lambda function that is run to fulfill the intent. 

    

    uri -> (string)

      

      The Amazon Resource Name (ARN) of the Lambda function.

      

      

    messageVersion -> (string)

      

      The version of the request-response that you want Amazon Lex to use to invoke your Lambda function. For more information, see  using-lambda .

      

      

    

  

parentIntentSignature -> (string)

  

  A unique identifier for the built-in intent that this intent is based on.

  

  

lastUpdatedDate -> (timestamp)

  

  The date that the intent was updated. When you create a resource, the creation date and last update dates are the same.

  

  

createdDate -> (timestamp)

  

  The date that the intent was created.

  

  

version -> (string)

  

  The version of the intent. For a new intent, the version is always ``$LATEST`` .

  

  

checksum -> (string)

  

  Checksum of the ``$LATEST`` version of the intent created or updated.

  

  

