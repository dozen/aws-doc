[ :ref:`aws <cli:aws>` . :ref:`lex-runtime <cli:aws lex-runtime>` ]

.. _cli:aws lex-runtime post-text:


*********
post-text
*********



===========
Description
===========



Sends user input (text-only) to Amazon Lex. Client applications can use this API to send requests to Amazon Lex at runtime. Amazon Lex then interprets the user input using the machine learning model it built for the bot. 

 

In response, Amazon Lex returns the next ``message`` to convey to the user an optional ``responseCard`` to display. Consider the following example messages: 

 

 
* For a user input "I would like a pizza", Amazon Lex might return a response with a message eliciting slot data (for example, PizzaSize): "What size pizza would you like?"  
 
* After the user provides all of the pizza order information, Amazon Lex might return a response with a message to obtain user confirmation "Proceed with the pizza order?".  
 
* After the user replies to a confirmation prompt with a "yes", Amazon Lex might return a conclusion statement: "Thank you, your cheese pizza has been ordered.".  
 

 

Not all Amazon Lex messages require a user response. For example, a conclusion statement does not require a response. Some messages require only a "yes" or "no" user response. In addition to the ``message`` , Amazon Lex provides additional context about the message in the response that you might use to enhance client behavior, for example, to display the appropriate client user interface. These are the ``slotToElicit`` , ``dialogState`` , ``intentName`` , and ``slots`` fields in the response. Consider the following examples: 

 

 
* If the message is to elicit slot data, Amazon Lex returns the following context information: 

   
  * ``dialogState`` set to ElicitSlot  
   
  * ``intentName`` set to the intent name in the current context  
   
  * ``slotToElicit`` set to the slot name for which the ``message`` is eliciting information  
   
  * ``slots`` set to a map of slots, configured for the intent, with currently known values  
   

 
 
* If the message is a confirmation prompt, the ``dialogState`` is set to ConfirmIntent and ``SlotToElicit`` is set to null.  
 
* If the message is a clarification prompt (configured for the intent) that indicates that user intent is not understood, the ``dialogState`` is set to ElicitIntent and ``slotToElicit`` is set to null.  
 

 

In addition, Amazon Lex also returns your application-specific ``sessionAttributes`` . For more information, see `Managing Conversation Context <http://docs.aws.amazon.com/lex/latest/dg/context-mgmt.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/runtime.lex-2016-11-28/PostText>`_


========
Synopsis
========

::

    post-text
  --bot-name <value>
  --bot-alias <value>
  --user-id <value>
  [--session-attributes <value>]
  --input-text <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bot-name`` (string)


  The name of the Amazon Lex bot.

  

``--bot-alias`` (string)


  The alias of the Amazon Lex bot.

  

``--user-id`` (string)


  The ID of the client application user. The application developer decides the user IDs. At runtime, each request must include the user ID. Typically, each of your application users should have a unique ID. Note the following considerations: 

   

   
  * If you want a user to start a conversation on one device and continue the conversation on another device, you might choose a user-specific identifier, such as a login or Amazon Cognito user ID (assuming your application is using Amazon Cognito).  
   
  * If you want the same user to be able to have two independent conversations on two different devices, you might choose a device-specific identifier, such as device ID, or some globally unique identifier.  
   

  

``--session-attributes`` (map)


  By using session attributes, a client application can pass contextual information in the request to Amazon Lex For example, 

   

   
  * In Getting Started Exercise 1, the example bot uses the ``price`` session attribute to maintain the price of the flowers ordered (for example, "Price":25). The code hook (the Lambda function) sets this attribute based on the type of flowers ordered. For more information, see `Review the Details of Information Flow <http://docs.aws.amazon.com/lex/latest/dg/gs-bp-details-after-lambda.html>`_ .  
   
  * In the BookTrip bot exercise, the bot uses the ``currentReservation`` session attribute to maintain slot data during the in-progress conversation to book a hotel or book a car. For more information, see `Details of Information Flow <http://docs.aws.amazon.com/lex/latest/dg/book-trip-detail-flow.html>`_ .  
   
  * You might use the session attributes (key, value pairs) to track the requestID of user requests. 
   

   

  Amazon Lex simply passes these session attributes to the Lambda functions configured for the intent.

   

  In your Lambda function, you can also use the session attributes for initialization and customization (prompts and response cards). Some examples are:

   

   
  * Initialization - In a pizza ordering bot, if you can pass the user location as a session attribute (for example, ``"Location" : "111 Maple street"`` ), then your Lambda function might use this information to determine the closest pizzeria to place the order (perhaps to set the storeAddress slot value).  
   
  * Personalize prompts - For example, you can configure prompts to refer to the user name. (For example, "Hey [FirstName], what toppings would you like?"). You can pass the user name as a session attribute (``"FirstName" : "Joe"`` ) so that Amazon Lex can substitute the placeholder to provide a personalize prompt to the user ("Hey Joe, what toppings would you like?").  
   

   

  .. note::

     

    Amazon Lex does not persist session attributes. 

     

    If you configure a code hook for the intent, Amazon Lex passes the incoming session attributes to the Lambda function. If you want Amazon Lex to return these session attributes back to the client, the Lambda function must return them. 

     

    If there is no code hook configured for the intent, Amazon Lex simply returns the session attributes back to the client application. 

     

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--input-text`` (string)


  The text that the user entered (Amazon Lex interprets this text).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

intentName -> (string)

  

  The current user intent that Amazon Lex is aware of.

  

  

slots -> (map)

  

  The intent slots (name/value pairs) that Amazon Lex detected so far from the user input in the conversation. 

  

  key -> (string)

    

    

  value -> (string)

    

    

  

sessionAttributes -> (map)

  

  A map of key-value pairs representing the session-specific context information.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

message -> (string)

  

  A message to convey to the user. It can come from the bot's configuration or a code hook (Lambda function). If the current intent is not configured with a code hook or the code hook returned ``Delegate`` as the ``dialogAction.type`` in its response, then Amazon Lex decides the next course of action and selects an appropriate message from the bot configuration based on the current user interaction context. For example, if Amazon Lex is not able to understand the user input, it uses a clarification prompt message (for more information, see the Error Handling section in the Amazon Lex console). Another example: if the intent requires confirmation before fulfillment, then Amazon Lex uses the confirmation prompt message in the intent configuration. If the code hook returns a message, Amazon Lex passes it as-is in its response to the client. 

  

  

dialogState -> (string)

  

  Identifies the current state of the user interaction. Amazon Lex returns one of the following values as ``dialogState`` . The client can optionally use this information to customize the user interface. 

   

   
  * ``ElicitIntent`` – Amazon Lex wants to elicit user intent.  For example, a user might utter an intent ("I want to order a pizza"). If Amazon Lex cannot infer the user intent from this utterance, it will return this dialogState. 
   
  * ``ConfirmIntent`` – Amazon Lex is expecting a "yes" or "no" response.  For example, Amazon Lex wants user confirmation before fulfilling an intent.  Instead of a simple "yes" or "no," a user might respond with additional information. For example, "yes, but make it thick crust pizza" or "no, I want to order a drink". Amazon Lex can process such additional information (in these examples, update the crust type slot value, or change intent from OrderPizza to OrderDrink). 
   
  * ``ElicitSlot`` – Amazon Lex is expecting a slot value for the current intent.  For example, suppose that in the response Amazon Lex sends this message: "What size pizza would you like?". A user might reply with the slot value (e.g., "medium"). The user might also provide additional information in the response (e.g., "medium thick crust pizza"). Amazon Lex can process such additional information appropriately.  
   
  * ``Fulfilled`` – Conveys that the Lambda function configured for the intent has successfully fulfilled the intent.  
   
  * ``ReadyForFulfillment`` – Conveys that the client has to fulfill the intent.  
   
  * ``Failed`` – Conveys that the conversation with the user failed.  This can happen for various reasons including that the user did not provide an appropriate response to prompts from the service (you can configure how many times Amazon Lex can prompt a user for specific information), or the Lambda function failed to fulfill the intent.  
   

  

  

slotToElicit -> (string)

  

  If the ``dialogState`` value is ``ElicitSlot`` , returns the name of the slot for which Amazon Lex is eliciting a value. 

  

  

responseCard -> (structure)

  

  Represents the options that the user has to respond to the current prompt. Response Card can come from the bot configuration (in the Amazon Lex console, choose the settings button next to a slot) or from a code hook (Lambda function). 

  

  version -> (string)

    

    The version of the response card format.

    

    

  contentType -> (string)

    

    The content type of the response.

    

    

  genericAttachments -> (list)

    

    An array of attachment objects representing options.

    

    (structure)

      

      Represents an option rendered to the user when a prompt is shown. It could be an image, a button, a link, or text. 

      

      title -> (string)

        

        The title of the option.

        

        

      subTitle -> (string)

        

        The subtitle shown below the title.

        

        

      attachmentLinkUrl -> (string)

        

        The URL of an attachment to the response card.

        

        

      imageUrl -> (string)

        

        The URL of an image that is displayed to the user.

        

        

      buttons -> (list)

        

        The list of options to show to the user.

        

        (structure)

          

          Represents an option to be shown on the client platform (Facebook, Slack, etc.)

          

          text -> (string)

            

            input-text that is visible to the user on the button.

            

            

          value -> (string)

            

            The value sent to Amazon Lex when a user chooses the button. For example, consider button text "NYC." When the user chooses the button, the value sent can be "New York City."

            

            

          

        

      

    

  

