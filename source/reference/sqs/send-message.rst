[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs send-message:


************
send-message
************



===========
Description
===========



Delivers a message to the specified queue. With Amazon SQS, you now have the ability to send large payload messages that are up to 256KB (262,144 bytes) in size. To send large payloads, you must use an AWS SDK that supports SigV4 signing. To verify whether SigV4 is supported for an AWS SDK, check the SDK release notes. 

 

.. warning::

   

  The following list shows the characters (in Unicode) allowed in your message, according to the W3C XML specification. For more information, go to `http\://www.w3.org/TR/REC-xml/#charsets`_ If you send any characters not included in the list, your request will be rejected. 

   

  #x9 | #xA | #xD | [#x20 to #xD7FF] | [#xE000 to #xFFFD] | [#x10000 to #x10FFFF] 

   



========
Synopsis
========

::

    send-message
  --queue-url <value>
  --message-body <value>
  [--delay-seconds <value>]
  [--message-attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to take action on.

  

``--message-body`` (string)


  The message to send. message-body maximum 256 KB in size. For a list of allowed characters, see the preceding important note.

  

``--delay-seconds`` (integer)


  The number of seconds (0 to 900 - 15 minutes) to delay a specific message. Messages with a positive ``DelaySeconds`` value become available for processing after the delay time is finished. If you don't specify a value, the default value for the queue applies. 

  

``--message-attributes`` (map)


  Each message attribute consists of a Name, Type, and Value. For more information, see `Message Attribute Items`_ .

  



Shorthand Syntax::

    KeyName1=StringValue=string,BinaryValue=blob,StringListValues=string,string,BinaryListValues=blob,blob,DataType=string,KeyName2=StringValue=string,BinaryValue=blob,StringListValues=string,string,BinaryListValues=blob,blob,DataType=string




JSON Syntax::

  {"string": {
        "StringValue": "string",
        "BinaryValue": blob,
        "StringListValues": ["string", ...],
        "BinaryListValues": [blob, ...],
        "DataType": "string"
      }
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To send a message**

This example sends a message with the specified message body, delay period, and message attributes, to the specified queue.

Command::

  aws sqs send-message --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue --message-body "Information about the largest city in Any Region." --delay-seconds 10 --message-attributes file://send-message.json

Input file (send-message.json)::

  {
    "City": {
      "DataType": "String",
      "StringValue": "Any City"
    },
    "Greeting": {
      "DataType": "Binary",
      "BinaryValue": "Hello, World!"
    },
    "Population": {
      "DataType": "Number",
      "StringValue": "1250800"
    }
  }

Output::

  {
    "MD5OfMessageBody": "51b0a325...39163aa0",
    "MD5OfMessageAttributes": "00484c68...59e48f06",
    "MessageId": "da68f62c-0c07-4bee-bf5f-7e856EXAMPLE"
  }




======
Output
======

MD5OfMessageBody -> (string)

  

  An MD5 digest of the non-URL-encoded message body string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

  

  

MD5OfMessageAttributes -> (string)

  

  An MD5 digest of the non-URL-encoded message attribute string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

  

  

MessageId -> (string)

  

  An element containing the message ID of the message sent to the queue. For more information, see `Queue and Message Identifiers`_ in the *Amazon SQS Developer Guide* . 

  

  



.. _http\://www.w3.org/TR/REC-xml/#charsets: http://www.w3.org/TR/REC-xml/#charsets
.. _Message Attribute Items: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSMessageAttributes.html#SQSMessageAttributesNTV
.. _http\://www.faqs.org/rfcs/rfc1321.html: http://www.faqs.org/rfcs/rfc1321.html
.. _Queue and Message Identifiers: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/ImportantIdentifiers.html
