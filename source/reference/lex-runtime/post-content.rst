[ :ref:`aws <cli:aws>` . :ref:`lex-runtime <cli:aws lex-runtime>` ]

.. _cli:aws lex-runtime post-content:


************
post-content
************



===========
Description
===========



Sends user input (text or speech) to Amazon Lex. Clients use this API to send requests to Amazon Lex at runtime. Amazon Lex interprets the user input using the machine learning model that it built for the bot. 

 

In response, Amazon Lex returns the next message to convey to the user. Consider the following example messages: 

 

 
* For a user input "I would like a pizza," Amazon Lex might return a response with a message eliciting slot data (for example, ``PizzaSize`` ): "What size pizza would you like?".  
 
* After the user provides all of the pizza order information, Amazon Lex might return a response with a message to get user confirmation: "Order the pizza?".  
 
* After the user replies "Yes" to the confirmation prompt, Amazon Lex might return a conclusion statement: "Thank you, your cheese pizza has been ordered.".  
 

 

Not all Amazon Lex messages require a response from the user. For example, conclusion statements do not require a response. Some messages require only a yes or no response. In addition to the ``message`` , Amazon Lex provides additional context about the message in the response that you can use to enhance client behavior, such as displaying the appropriate client user interface. Consider the following examples: 

 

 
* If the message is to elicit slot data, Amazon Lex returns the following context information:  

   
  * ``x-amz-lex-dialog-state`` header set to ``ElicitSlot``   
   
  * ``x-amz-lex-intent-name`` header set to the intent name in the current context  
   
  * ``x-amz-lex-slot-to-elicit`` header set to the slot name for which the ``message`` is eliciting information  
   
  * ``x-amz-lex-slots`` header set to a map of slots configured for the intent with their current values  
   

 
 
* If the message is a confirmation prompt, the ``x-amz-lex-dialog-state`` header is set to ``Confirmation`` and the ``x-amz-lex-slot-to-elicit`` header is omitted.  
 
* If the message is a clarification prompt configured for the intent, indicating that the user intent is not understood, the ``x-amz-dialog-state`` header is set to ``ElicitIntent`` and the ``x-amz-slot-to-elicit`` header is omitted.  
 

 

In addition, Amazon Lex also returns your application-specific ``sessionAttributes`` . For more information, see `Managing Conversation Context <http://docs.aws.amazon.com/lex/latest/dg/context-mgmt.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/runtime.lex-2016-11-28/PostContent>`_


========
Synopsis
========

::

    post-content
  --bot-name <value>
  --bot-alias <value>
  --user-id <value>
  [--session-attributes <value>]
  --content-type <value>
  [--accept <value>]
  --input-stream <value>
  outfile <value>




=======
Options
=======

``--bot-name`` (string)


  Name of the Amazon Lex bot.

  

``--bot-alias`` (string)


  Alias of the Amazon Lex bot.

  

``--user-id`` (string)


  ID of the client application user. Typically, each of your application users should have a unique ID. The application developer decides the user IDs. At runtime, each request must include the user ID. Note the following considerations:

   

   
  * If you want a user to start conversation on one device and continue the conversation on another device, you might choose a user-specific identifier, such as the user's login, or Amazon Cognito user ID (assuming your application is using Amazon Cognito).  
   
  * If you want the same user to be able to have two independent conversations on two different devices, you might choose device-specific identifier, such as device ID, or some globally unique identifier.  
   

  

``--session-attributes`` (JSON)


  You pass this value in the ``x-amz-lex-session-attributes`` HTTP header. The value must be map (keys and values must be strings) that is JSON serialized and then base64 encoded.

   

  A session represents dialog between a user and Amazon Lex. At runtime, a client application can pass contextual information, in the request to Amazon Lex. For example, 

   

   
  * You might use session attributes to track the requestID of user requests. 
   
  * In Getting Started Exercise 1, the example bot uses the price session attribute to maintain the price of flowers ordered (for example, "price":25). The code hook (Lambda function) sets this attribute based on the type of flowers ordered. For more information, see `Review the Details of Information Flow <http://docs.aws.amazon.com/lex/latest/dg/gs-bp-details-after-lambda.html>`_ .  
   
  * In the BookTrip bot exercise, the bot uses the ``currentReservation`` session attribute to maintains the slot data during the in-progress conversation to book a hotel or book a car. For more information, see `Details of Information Flow <http://docs.aws.amazon.com/lex/latest/dg/book-trip-detail-flow.html>`_ .  
   

   

  Amazon Lex passes these session attributes to the Lambda functions configured for the intent In the your Lambda function, you can use the session attributes for initialization and customization (prompts). Some examples are: 

   

   
  * Initialization - In a pizza ordering bot, if you pass user location (for example, ``"Location : 111 Maple Street"`` ), then your Lambda function might use this information to determine the closest pizzeria to place the order (and perhaps set the storeAddress slot value as well).  Personalized prompts - For example, you can configure prompts to refer to the user by name (for example, "Hey [firstName], what toppings would you like?"). You can pass the user's name as a session attribute ("firstName": "Joe") so that Amazon Lex can substitute the placeholder to provide a personalized prompt to the user ("Hey Joe, what toppings would you like?").  
   

   

  .. note::

     

    Amazon Lex does not persist session attributes. 

     

    If you configured a code hook for the intent, Amazon Lex passes the incoming session attributes to the Lambda function. The Lambda function must return these session attributes if you want Amazon Lex to return them to the client. 

     

    If there is no code hook configured for the intent Amazon Lex simply returns the session attributes to the client application. 

     

  

``--content-type`` (string)


  You pass this values as the ``Content-Type`` HTTP header. 

   

  Indicates the audio format or text. The header value must start with one of the following prefixes: 

   

   
  * PCM format 

     
    * audio/l16; rate=16000; channels=1 
     
    * audio/x-l16; sample-rate=16000; channel-count=1 
     

   
   
  * Opus format 

     
    * audio/x-cbr-opus-with-preamble; preamble-size=0; bit-rate=1; frame-size-milliseconds=1.1 
     

   
   
  * Text format 

     
    * text/plain; charset=utf-8 
     

   
   

  

``--accept`` (string)


  You pass this value as the ``accept`` HTTP header. 

   

  The message Amazon Lex returns in the response can be either text or speech based on the ``accept`` HTTP header value in the request. 

   

   
  * If the value is ``text/plain; charset=utf-8`` , Amazon Lex returns text in the response.  
   
  * If the value begins with ``audio/`` , Amazon Lex returns speech in the response. Amazon Lex uses Amazon Polly to generate the speech (using the configuration you specified in the ``accept`` header). For example, if you specify ``audio/mpeg`` as the value, Amazon Lex returns speech in the MPEG format. The following are the accepted values: 

     
    * audio/mpeg 
     
    * audio/ogg 
     
    * audio/pcm 
     
    * text/plain; charset=utf-8 
     
    * audio/* (defaults to mpeg) 
     

   
   

  

``--input-stream`` (blob)


  User input in PCM or Opus audio format or text format as described in the ``Content-Type`` HTTP header. 

  

``outfile`` (string)
Filename where the content will be saved



======
Output
======

contentType -> (string)

  

  Content type as specified in the ``accept`` HTTP header in the request.

  

  

intentName -> (string)

  

  Current user intent that Amazon Lex is aware of.

  

  

slots -> (JSON)

  

  Map of zero or more intent slots (name/value pairs) Amazon Lex detected from the user input during the conversation.

  

  

sessionAttributes -> (JSON)

  

  Map of key/value pairs representing the session-specific context information. 

  

  

message -> (string)

  

  Message to convey to the user. It can come from the bot's configuration or a code hook (Lambda function). If the current intent is not configured with a code hook or if the code hook returned ``Delegate`` as the ``dialogAction.type`` in its response, then Amazon Lex decides the next course of action and selects an appropriate message from the bot configuration based on the current user interaction context. For example, if Amazon Lex is not able to understand the user input, it uses a clarification prompt message (For more information, see the Error Handling section in the Amazon Lex console). Another example: if the intent requires confirmation before fulfillment, then Amazon Lex uses the confirmation prompt message in the intent configuration. If the code hook returns a message, Amazon Lex passes it as-is in its response to the client. 

  

  

dialogState -> (string)

  

  Identifies the current state of the user interaction. Amazon Lex returns one of the following values as ``dialogState`` . The client can optionally use this information to customize the user interface. 

   

   
  * ``ElicitIntent`` – Amazon Lex wants to elicit the user's intent. Consider the following examples:  For example, a user might utter an intent ("I want to order a pizza"). If Amazon Lex cannot infer the user intent from this utterance, it will return this dialog state.  
   
  * ``ConfirmIntent`` – Amazon Lex is expecting a "yes" or "no" response.  For example, Amazon Lex wants user confirmation before fulfilling an intent. Instead of a simple "yes" or "no" response, a user might respond with additional information. For example, "yes, but make it a thick crust pizza" or "no, I want to order a drink." Amazon Lex can process such additional information (in these examples, update the crust type slot or change the intent from OrderPizza to OrderDrink).  
   
  * ``ElicitSlot`` – Amazon Lex is expecting the value of a slot for the current intent.  For example, suppose that in the response Amazon Lex sends this message: "What size pizza would you like?". A user might reply with the slot value (e.g., "medium"). The user might also provide additional information in the response (e.g., "medium thick crust pizza"). Amazon Lex can process such additional information appropriately.  
   
  * ``Fulfilled`` – Conveys that the Lambda function has successfully fulfilled the intent.  
   
  * ``ReadyForFulfillment`` – Conveys that the client has to fullfill the request.  
   
  * ``Failed`` – Conveys that the conversation with the user failed.  This can happen for various reasons, including that the user does not provide an appropriate response to prompts from the service (you can configure how many times Amazon Lex can prompt a user for specific information), or if the Lambda function fails to fulfill the intent.  
   

  

  

slotToElicit -> (string)

  

  If the ``dialogState`` value is ``ElicitSlot`` , returns the name of the slot for which Amazon Lex is eliciting a value. 

  

  

inputTranscript -> (string)

  

  Transcript of the voice input to the operation.

  

  

audioStream -> (blob)

  

  The prompt (or statement) to convey to the user. This is based on the bot configuration and context. For example, if Amazon Lex did not understand the user intent, it sends the ``clarificationPrompt`` configured for the bot. If the intent requires confirmation before taking the fulfillment action, it sends the ``confirmationPrompt`` . Another example: Suppose that the Lambda function successfully fulfilled the intent, and sent a message to convey to the user. Then Amazon Lex sends that message in the response. 

  

  

