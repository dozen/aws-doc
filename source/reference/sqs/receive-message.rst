[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs receive-message:


***************
receive-message
***************



===========
Description
===========



Retrieves one or more messages (up to 10), from the specified queue. Using the ``WaitTimeSeconds`` parameter enables long-poll support. For more information, see `Amazon SQS Long Polling <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-long-polling.html>`_ in the *Amazon SQS Developer Guide* . 

 

Short poll is the default behavior where a weighted random set of machines is sampled on a ``receive-message`` call. Thus, only the messages on the sampled machines are returned. If the number of messages in the queue is small (fewer than 1,000), you most likely get fewer messages than you requested per ``receive-message`` call. If the number of messages in the queue is extremely small, you might not receive any messages in a particular ``receive-message`` response. If this happens, repeat the request. 

 

For each message returned, the response includes the following:

 

 
* The message body. 
 
* An MD5 digest of the message body. For information about MD5, see `RFC1321 <https://www.ietf.org/rfc/rfc1321.txt>`_ . 
 
* The ``MessageId`` you received when you sent the message to the queue. 
 
* The receipt handle. 
 
* The message attributes. 
 
* An MD5 digest of the message attributes. 
 

 

The receipt handle is the identifier you must provide when deleting the message. For more information, see `Queue and Message Identifiers <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-queue-message-identifiers.html>`_ in the *Amazon SQS Developer Guide* .

 

You can provide the ``VisibilityTimeout`` parameter in your request. The parameter is applied to the messages that Amazon SQS returns in the response. If you don't include the parameter, the overall visibility timeout for the queue is used for the returned messages. For more information, see `Visibility Timeout <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html>`_ in the *Amazon SQS Developer Guide* .

 

A message that isn't deleted or a message whose visibility isn't extended before the visibility timeout expires counts as a failed receive. Depending on the configuration of the queue, the message might be sent to the dead letter queue.

 

.. note::

   

  In the future, new attributes might be added. If you write code that calls this action, we recommend that you structure your code so that it can handle new attributes gracefully.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/ReceiveMessage>`_


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
  [--receive-request-attempt-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue from which messages are received.

   

  Queue URLs are case-sensitive.

  

``--attribute-names`` (list)


  A list of attributes that need to be returned along with each message. These attributes include:

   

   
  * ``All`` - Returns all values. 
   
  * ``ApproximateFirstReceiveTimestamp`` - Returns the time the message was first received from the queue (`epoch time <http://en.wikipedia.org/wiki/Unix_time>`_ in milliseconds). 
   
  * ``ApproximateReceiveCount`` - Returns the number of times a message has been received from the queue but not deleted. 
   
  * ``SenderId``   

     
    * For an IAM user, returns the IAM user ID, for example ``ABCDEFGHI1JKLMNOPQ23R`` . 
     
    * For an IAM role, returns the IAM role ID, for example ``ABCDE1F2GH3I4JK5LMNOP:i-a123b456`` . 
     

   
   
  * ``SentTimestamp`` - Returns the time the message was sent to the queue (`epoch time <http://en.wikipedia.org/wiki/Unix_time>`_ in milliseconds). 
   
  * ``MessageDeduplicationId`` - Returns the value provided by the sender that calls the ``  send-message `` action. 
   
  * ``MessageGroupId`` - Returns the value provided by the sender that calls the ``  send-message `` action. Messages with the same ``MessageGroupId`` are returned in sequence. 
   
  * ``SequenceNumber`` - Returns the value provided by Amazon SQS. 
   

   

  Any other valid special request parameters (such as the following) are ignored:

   

   
  * ``ApproximateNumberOfMessages``   
   
  * ``ApproximateNumberOfMessagesDelayed``   
   
  * ``ApproximateNumberOfMessagesNotVisible``   
   
  * ``CreatedTimestamp``   
   
  * ``ContentBasedDeduplication``   
   
  * ``DelaySeconds``   
   
  * ``FifoQueue``   
   
  * ``LastModifiedTimestamp``   
   
  * ``MaximumMessageSize``   
   
  * ``MessageRetentionPeriod``   
   
  * ``Policy``   
   
  * ``QueueArn`` ,  
   
  * ``ReceiveMessageWaitTimeSeconds``   
   
  * ``RedrivePolicy``   
   
  * ``VisibilityTimeout``   
   

  



Syntax::

  "string" "string" ...

  Where valid values are:
    All
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
    FifoQueue
    ContentBasedDeduplication
    KmsMasterKeyId
    KmsDataKeyReusePeriodSeconds





``--message-attribute-names`` (list)


  The name of the message attribute, where *N* is the index.

   

   
  * The name can contain alphanumeric characters and the underscore (``_`` ), hyphen (``-`` ), and period (``.`` ). 
   
  * The name is case-sensitive and must be unique among all attribute names for the message. 
   
  * The name must not start with AWS-reserved prefixes such as ``AWS.`` or ``Amazon.`` (or any casing variants). 
   
  * The name must not start or end with a period (``.`` ), and it should not have periods in succession (``..`` ). 
   
  * The name can be up to 256 characters long. 
   

   

  When using ``receive-message`` , you can send a list of attribute names to receive, or you can return all of the attributes by specifying ``All`` or ``.*`` in your request. You can also use all message attributes starting with a prefix, for example ``bar.*`` .

  



Syntax::

  "string" "string" ...



``--max-number-of-messages`` (integer)


  The maximum number of messages to return. Amazon SQS never returns more messages than this value (however, fewer messages might be returned). Valid values are 1 to 10. Default is 1.

  

``--visibility-timeout`` (integer)


  The duration (in seconds) that the received messages are hidden from subsequent retrieve requests after being retrieved by a ``receive-message`` request.

  

``--wait-time-seconds`` (integer)


  The duration (in seconds) for which the call waits for a message to arrive in the queue before returning. If a message is available, the call returns sooner than ``WaitTimeSeconds`` .

  

``--receive-request-attempt-id`` (string)


  This parameter applies only to FIFO (first-in-first-out) queues.

   

  The token used for deduplication of ``receive-message`` calls. If a networking issue occurs after a ``receive-message`` action, and instead of a response you receive a generic error, you can retry the same action with an identical ``ReceiveRequestAttemptId`` to retrieve the same set of messages, even if their visibility timeout has not yet expired.

   

   
  * You can use ``ReceiveRequestAttemptId`` only for 5 minutes after a ``receive-message`` action. 
   
  * When you set ``FifoQueue`` , a caller of the ``receive-message`` action can provide a ``ReceiveRequestAttemptId`` explicitly. 
   
  * If a caller of the ``receive-message`` action doesn't provide a ``ReceiveRequestAttemptId`` , Amazon SQS generates a ``ReceiveRequestAttemptId`` . 
   
  * You can retry the ``receive-message`` action with the same ``ReceiveRequestAttemptId`` if none of the messages have been modified (deleted or had their visibility changes). 
   
  * During a visibility timeout, subsequent calls with the same ``ReceiveRequestAttemptId`` return the same messages and receipt handles. If a retry occurs within the deduplication interval, it resets the visibility timeout. For more information, see `Visibility Timeout <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html>`_ in the *Amazon Simple Queue Service Developer Guide* . 

  .. warning::

     If a caller of the ``receive-message`` action is still processing messages when the visibility timeout expires and messages become visible, another worker reading from the same queue can receive the same messages and therefore process duplicates. Also, if a reader whose message processing time is longer than the visibility timeout tries to delete the processed messages, the action fails with an error. To mitigate this effect, ensure that your application observes a safe threshold before the visibility timeout expires and extend the visibility timeout as necessary. 

   
   
  * While messages with a particular ``MessageGroupId`` are invisible, no more messages belonging to the same ``MessageGroupId`` are returned until the visibility timeout expires. You can still receive messages with another ``MessageGroupId`` as long as it is also visible. 
   
  * If a caller of ``receive-message`` can't track the ``ReceiveRequestAttemptId`` , no retries work until the original visibility timeout expires. As a result, delays might occur but the messages in the queue remain in a strict order. 
   

   

  The length of ``ReceiveRequestAttemptId`` is 128 characters. ``ReceiveRequestAttemptId`` can contain alphanumeric characters (``a-z`` , ``A-Z`` , ``0-9`` ) and punctuation (``!"#$%'()*+,-./:;=?@[\]^_`{|}~`` ).

   

  For best practices of using ``ReceiveRequestAttemptId`` , see `Using the ReceiveRequestAttemptId Request Parameter <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queue-recommendations.html#using-receiverequestattemptid-request-parameter>`_ in the *Amazon Simple Queue Service Developer Guide* .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      A unique identifier for the message. A ``MessageId`` is considered unique across all AWS accounts for an extended period of time.

      

      

    ReceiptHandle -> (string)

      

      An identifier associated with the act of receiving the message. A new receipt handle is returned every time you receive a message. When deleting a message, you provide the last received receipt handle to delete the message.

      

      

    MD5OfBody -> (string)

      

      An MD5 digest of the non-URL-encoded message body string.

      

      

    Body -> (string)

      

      The message's contents (not URL-encoded).

      

      

    Attributes -> (map)

      

       ``SenderId`` , ``SentTimestamp`` , ``ApproximateReceiveCount`` , and/or ``ApproximateFirstReceiveTimestamp`` . ``SentTimestamp`` and ``ApproximateFirstReceiveTimestamp`` are each returned as an integer representing the `epoch time <http://en.wikipedia.org/wiki/Unix_time>`_ in milliseconds.

      

      Name -> (string)

        

        

      Value -> (string)

        

        

      

    MD5OfMessageAttributes -> (string)

      

      An MD5 digest of the non-URL-encoded message attribute string. You can use this attribute to verify that Amazon SQS received the message correctly. Amazon SQS URL-decodes the message before creating the MD5 digest. For information about MD5, see `RFC1321 <https://www.ietf.org/rfc/rfc1321.txt>`_ .

      

      

    MessageAttributes -> (map)

      

      Each message attribute consists of a ``Name`` , ``Type`` , and ``Value`` . For more information, see `Message Attribute Items and Validation <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-message-attributes.html#message-attributes-items-validation>`_ in the *Amazon SQS Developer Guide* .

      

      Name -> (string)

        

        

      Value -> (structure)

        

        The user-specified message attribute value. For string data types, the ``Value`` attribute has the same restrictions on the content as the message body. For more information, see ``  send-message .``  

         

         ``Name`` , ``type`` , ``value`` and the message body must not be empty or null. All parts of the message attribute, including ``Name`` , ``Type`` , and ``Value`` , are part of the message size restriction (256 KB or 262,144 bytes).

        

        StringValue -> (string)

          

          Strings are Unicode with UTF-8 binary encoding. For a list of code values, see `ASCII Printable Characters <http://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters>`_ .

          

          

        BinaryValue -> (blob)

          

          Binary type attributes can store any binary data, such as compressed data, encrypted data, or images.

          

          

        StringListValues -> (list)

          

          Not implemented. Reserved for future use.

          

          (string)

            

            

          

        BinaryListValues -> (list)

          

          Not implemented. Reserved for future use.

          

          (blob)

            

            

          

        DataType -> (string)

          

          Amazon SQS supports the following logical data types: ``queue-url`` , ``Number`` , and ``Binary`` . For the ``Number`` data type, you must use ``StringValue`` .

           

          You can also append custom labels. For more information, see `Message Attribute Data Types and Validation <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-message-attributes.html#message-attributes-data-types-validation>`_ in the *Amazon SQS Developer Guide* .

          

          

        

      

    

  

