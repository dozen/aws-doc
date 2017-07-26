[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns publish:


*******
publish
*******



===========
Description
===========



Sends a message to all of a topic's subscribed endpoints. When a ``messageId`` is returned, the message has been saved and Amazon SNS will attempt to deliver it to the topic's subscribers shortly. The format of the outgoing message to each subscribed endpoint depends on the notification protocol.

 

To use the ``publish`` action for sending a message to a mobile endpoint, such as an app on a Kindle device or mobile phone, you must specify the EndpointArn for the TargetArn parameter. The EndpointArn is returned when making a call with the ``create-platform-endpoint`` action. 

 

For more information about formatting messages, see `Send Custom Platform-Specific Payloads in Messages to Mobile Devices <http://docs.aws.amazon.com/sns/latest/dg/mobile-push-send-custommessage.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/Publish>`_


========
Synopsis
========

::

    publish
  [--topic-arn <value>]
  [--target-arn <value>]
  [--phone-number <value>]
  --message <value>
  [--subject <value>]
  [--message-structure <value>]
  [--message-attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--topic-arn`` (string)


  The topic you want to publish to.

   

  If you don't specify a value for the ``TopicArn`` parameter, you must specify a value for the ``PhoneNumber`` or ``TargetArn`` parameters.

  

``--target-arn`` (string)


  Either TopicArn or EndpointArn, but not both.

   

  If you don't specify a value for the ``TargetArn`` parameter, you must specify a value for the ``PhoneNumber`` or ``TopicArn`` parameters.

  

``--phone-number`` (string)


  The phone number to which you want to deliver an SMS message. Use E.164 format.

   

  If you don't specify a value for the ``PhoneNumber`` parameter, you must specify a value for the ``TargetArn`` or ``TopicArn`` parameters.

  

``--message`` (string)


  The message you want to send to the topic.

   

  If you want to send the same message to all transport protocols, include the text of the message as a target-arn value.

   

  If you want to send different messages for each transport protocol, set the value of the ``MessageStructure`` parameter to ``json`` and use a JSON object for the ``Message`` parameter. 

   

  Constraints: Messages must be UTF-8 encoded strings at most 256 KB in size (262144 bytes, not 262144 characters).

   

  JSON-specific constraints:

   

   
  * Keys in the JSON object that correspond to supported transport protocols must have simple JSON string values. 
   
  * The values will be parsed (unescaped) before they are used in outgoing messages. 
   
  * Outbound notifications are JSON encoded (meaning that the characters will be reescaped for sending). 
   
  * Values have a minimum length of 0 (the empty string, "", is allowed). 
   
  * Values have a maximum length bounded by the overall message size (so, including multiple protocols may limit message sizes). 
   
  * Non-string values will cause the key to be ignored. 
   
  * Keys that do not correspond to supported transport protocols are ignored. 
   
  * Duplicate keys are not allowed. 
   
  * Failure to parse or validate any key or value in the message will cause the ``publish`` call to return an error (no partial delivery). 
   

  

``--subject`` (string)


  Optional parameter to be used as the "Subject" line when the message is delivered to email endpoints. This field will also be included, if present, in the standard JSON messages delivered to other endpoints.

   

  Constraints: Subjects must be ASCII text that begins with a letter, number, or punctuation mark; must not include line breaks or control characters; and must be less than 100 characters long.

  

``--message-structure`` (string)


  Set ``MessageStructure`` to ``json`` if you want to send a different message for each protocol. For example, using one publish action, you can send a short message to your SMS subscribers and a longer message to your email subscribers. If you set ``MessageStructure`` to ``json`` , the value of the ``Message`` parameter must: 

   

   
  * be a syntactically valid JSON object; and 
   
  * contain at least a top-level JSON key of "default" with a value that is a string. 
   

   

  You can define other top-level keys that define the message you want to send to a specific transport protocol (e.g., "http").

   

  For information about sending different messages for each protocol using the AWS Management Console, go to `Create Different Messages for Each Protocol <http://docs.aws.amazon.com/sns/latest/gsg/Publish.html#sns-message-formatting-by-protocol>`_ in the *Amazon Simple Notification Service Getting Started Guide* . 

   

  Valid value: ``json``  

  

``--message-attributes`` (map)


  Message attributes for publish action.

  



Shorthand Syntax::

    KeyName1=DataType=string,StringValue=string,BinaryValue=blob,KeyName2=DataType=string,StringValue=string,BinaryValue=blob




JSON Syntax::

  {"string": {
        "DataType": "string",
        "StringValue": "string",
        "BinaryValue": blob
      }
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command publishes a message to an SNS topic named ``my-topic``::

  aws sns publish --topic-arn "arn:aws:sns:us-west-2:0123456789012:my-topic" --message file://message.txt

``message.txt`` is a text file containing the message to publish::

  Hello World
  Second Line

Putting the message in a text file allows you to include line breaks.

======
Output
======

MessageId -> (string)

  

  Unique identifier assigned to the published message.

   

  Length Constraint: Maximum 100 characters

  

  

