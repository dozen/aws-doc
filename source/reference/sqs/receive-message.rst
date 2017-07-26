[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs receive-message:


***************
receive-message
***************



===========
Description
===========



Retrieves one or more messages, with a maximum limit of 10 messages, from the specified queue. Long poll support is enabled by using the ``WaitTimeSeconds`` parameter. For more information, see `Amazon SQS Long Poll`_ in the *Amazon SQS Developer Guide* . 

 

Short poll is the default behavior where a weighted random set of machines is sampled on a ``receive-message`` call. This means only the messages on the sampled machines are returned. If the number of messages in the queue is small (less than 1000), it is likely you will get fewer messages than you requested per ``receive-message`` call. If the number of messages in the queue is extremely small, you might not receive any messages in a particular ``receive-message`` response; in which case you should repeat the request. 

 

For each message returned, the response includes the following: 

 

 
* Message body  
 
* MD5 digest of the message body. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .  
 
* Message ID you received when you sent the message to the queue.  
 
* Receipt handle.  
 
* Message attributes.  
 
* MD5 digest of the message attributes.  
 

 

The receipt handle is the identifier you must provide when deleting the message. For more information, see `Queue and Message Identifiers`_ in the *Amazon SQS Developer Guide* . 

 

You can provide the ``VisibilityTimeout`` parameter in your request, which will be applied to the messages that Amazon SQS returns in the response. If you do not include the parameter, the overall visibility timeout for the queue is used for the returned messages. For more information, see `Visibility Timeout`_ in the *Amazon SQS Developer Guide* . 

 

.. note::

   

  Going forward, new attributes might be added. If you are writing code that calls this action, we recommend that you structure your code so that it can handle new attributes gracefully. 

   



========
Synopsis
========

::

    receive-message
  --queue-url <value>
  [--attribute-names <value>]
  [--message-attribute-names <value>]
  [--max-number-of-messages <value>]
  [--visibility-timeout <value>]
  [--wait-time-seconds <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to take action on.

  

``--attribute-names`` (list)


  A list of attributes that need to be returned along with each message. 

   

  The following lists the names and descriptions of the attributes that can be returned: 

   

   
  * ``All`` - returns all values.
   
  * ``ApproximateFirstReceiveTimestamp`` - returns the time when the message was first received from the queue (epoch time in milliseconds).
   
  * ``ApproximateReceiveCount`` - returns the number of times a message has been received from the queue but not deleted.
   
  * ``SenderId`` - returns the AWS account number (or the IP address, if anonymous access is allowed) of the sender.
   
  * ``SentTimestamp`` - returns the time when the message was sent to the queue (epoch time in milliseconds).
   

  



Syntax::

  "string" "string" ...

  Where valid values are:
    Policy
    VisibilityTimeout
    MaximumMessageSize
    MessageRetentionPeriod
    ApproximateNumberOfMessages
    ApproximateNumberOfMessagesNotVisible
    CreatedTimestamp
    LastModifiedTimestamp
    QueueArn
    ApproximateNumberOfMessagesDelayed
    DelaySeconds
    ReceiveMessageWaitTimeSeconds
    RedrivePolicy





``--message-attribute-names`` (list)


  The name of the message attribute, where *N* is the index. The message attribute name can contain the following characters: A-Z, a-z, 0-9, underscore (_), hyphen (-), and period (.). The name must not start or end with a period, and it should not have successive periods. The name is case sensitive and must be unique among all attribute names for the message. The name can be up to 256 characters long. The name cannot start with "AWS." or "Amazon." (or any variations in casing), because these prefixes are reserved for use by Amazon Web Services.

   

  When using ``receive-message`` , you can send a list of attribute names to receive, or you can return all of the attributes by specifying "All" or ".*" in your request. You can also use "foo.*" to return all message attributes starting with the "foo" prefix.

  



Syntax::

  "string" "string" ...



``--max-number-of-messages`` (integer)


  The maximum number of messages to return. Amazon SQS never returns more messages than this value but may return fewer. Values can be from 1 to 10. Default is 1.

   

  All of the messages are not necessarily returned.

  

``--visibility-timeout`` (integer)


  The duration (in seconds) that the received messages are hidden from subsequent retrieve requests after being retrieved by a ``receive-message`` request.

  

``--wait-time-seconds`` (integer)


  The duration (in seconds) for which the call will wait for a message to arrive in the queue before returning. If a message is available, the call will return sooner than WaitTimeSeconds.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To receive a message**

This example receives up to 10 available messages, returning all available attributes.

Command::

  aws sqs receive-message --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue --attribute-names All --message-attribute-names All --max-number-of-messages 10 

Output::

  {
    "Messages": [
      {
        "Body": "My first message.",
        "ReceiptHandle": "AQEBzbVv...fqNzFw==",
        "MD5OfBody": "1000f835...a35411fa",
        "MD5OfMessageAttributes": "9424c491...26bc3ae7",
        "MessageId": "d6790f8d-d575-4f01-bc51-40122EXAMPLE",
        "Attributes": {
          "ApproximateFirstReceiveTimestamp": "1442428276921",
          "SenderId": "AIDAIAZKMSNQ7TEXAMPLE",
          "ApproximateReceiveCount": "5",
          "SentTimestamp": "1442428276921"
        },
        "MessageAttributes": {
          "PostalCode": {
            "DataType": "String",
            "StringValue": "ABC123"
          },
          "City": {
            "DataType": "String",
            "StringValue": "Any City"
          }
        }
      }
    ]
  }
  
This example receives the next available message, returning only the SenderId and SentTimestamp attributes as well as the PostalCode message attribute.

Command::

  aws sqs receive-message --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue --attribute-names SenderId SentTimestamp --message-attribute-names PostalCode 

Output::

  {
    "Messages": [
      {
        "Body": "My first message.",
        "ReceiptHandle": "AQEB6nR4...HzlvZQ==",
        "MD5OfBody": "1000f835...a35411fa",
        "MD5OfMessageAttributes": "b8e89563...e088e74f",
        "MessageId": "d6790f8d-d575-4f01-bc51-40122EXAMPLE",
        "Attributes": {
          "SenderId": "AIDAIAZKMSNQ7TEXAMPLE",
          "SentTimestamp": "1442428276921"
        },
        "MessageAttributes": {
          "PostalCode": {
            "DataType": "String",
            "StringValue": "ABC123"
          }
        }
      }
    ]
  }

======
Output
======

Messages -> (list)

  

  A list of messages.

  

  (structure)

    

    An Amazon SQS message.

    

    MessageId -> (string)

      

      A unique identifier for the message. Message IDs are considered unique across all AWS accounts for an extended period of time.

      

      

    ReceiptHandle -> (string)

      

      An identifier associated with the act of receiving the message. A new receipt handle is returned every time you receive a message. When deleting a message, you provide the last received receipt handle to delete the message.

      

      

    MD5OfBody -> (string)

      

      An MD5 digest of the non-URL-encoded message body string.

      

      

    Body -> (string)

      

      The message's contents (not URL-encoded).

      

      

    Attributes -> (map)

      

      ``SenderId`` , ``SentTimestamp`` , ``ApproximateReceiveCount`` , and/or ``ApproximateFirstReceiveTimestamp`` . ``SentTimestamp`` and ``ApproximateFirstReceiveTimestamp`` are each returned as an integer representing the `epoch time`_ in milliseconds.

      

      Name -> (string)

        

        The name of a queue attribute.

        

        

      Value -> (string)

        

        The value of a queue attribute.

        

        

      

    MD5OfMessageAttributes -> (string)

      

      An MD5 digest of the non-URL-encoded message attribute string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

      

      

    MessageAttributes -> (map)

      

      Each message attribute consists of a Name, Type, and Value. For more information, see `Message Attribute Items`_ .

      

      Name -> (string)

        

        

      Value -> (structure)

        

        The user-specified message attribute value. For string data types, the value attribute has the same restrictions on the content as the message body. For more information, see `send-message`_ .

         

        Name, type, and value must not be empty or null. In addition, the message body should not be empty or null. All parts of the message attribute, including name, type, and value, are included in the message size restriction, which is currently 256 KB (262,144 bytes).

        

        StringValue -> (string)

          

          Strings are Unicode with UTF8 binary encoding. For a list of code values, see `http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters`_ .

          

          

        BinaryValue -> (blob)

          

          Binary type attributes can store any binary data, for example, compressed data, encrypted data, or images.

          

          

        StringListValues -> (list)

          

          Not implemented. Reserved for future use.

          

          (string)

            

            

          

        BinaryListValues -> (list)

          

          Not implemented. Reserved for future use.

          

          (blob)

            

            

          

        DataType -> (string)

          

          Amazon SQS supports the following logical data types: String, Number, and Binary. In addition, you can append your own custom labels. For more information, see `Message Attribute Data Types`_ .

          

          

        

      

    

  



.. _epoch time: http://en.wikipedia.org/wiki/Unix_time
.. _Message Attribute Data Types: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSMessageAttributes.html#SQSMessageAttributes.DataTypes
.. _Amazon SQS Long Poll: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-long-polling.html
.. _Visibility Timeout: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/AboutVT.html
.. _Message Attribute Items: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSMessageAttributes.html#SQSMessageAttributesNTV
.. _send-message: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/APIReference/API_SendMessage.html
.. _http\://www.faqs.org/rfcs/rfc1321.html: http://www.faqs.org/rfcs/rfc1321.html
.. _Queue and Message Identifiers: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/ImportantIdentifiers.html
.. _http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters: http://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters
