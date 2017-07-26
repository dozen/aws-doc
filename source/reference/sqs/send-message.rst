[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs send-message:


************
send-message
************



===========
Description
===========



Delivers a message to the specified queue.

 

.. warning::

   

  A message can include only XML, JSON, and unformatted text. The following Unicode characters are allowed:

   

   ``#x9`` | ``#xA`` | ``#xD`` | ``#x20`` to ``#xD7FF`` | ``#xE000`` to ``#xFFFD`` | ``#x10000`` to ``#x10FFFF``  

   

  Any characters not included in this list will be rejected. For more information, see the `W3C specification for characters <http://www.w3.org/TR/REC-xml/#charsets>`_ .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/SendMessage>`_


========
Synopsis
========

::

    send-message
  --queue-url <value>
  --message-body <value>
  [--delay-seconds <value>]
  [--message-attributes <value>]
  [--message-deduplication-id <value>]
  [--message-group-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to which a message is sent.

   

  Queue URLs are case-sensitive.

  

``--message-body`` (string)


  The message to send. The maximum string size is 256 KB.

   

  .. warning::

     

    A message can include only XML, JSON, and unformatted text. The following Unicode characters are allowed:

     

     ``#x9`` | ``#xA`` | ``#xD`` | ``#x20`` to ``#xD7FF`` | ``#xE000`` to ``#xFFFD`` | ``#x10000`` to ``#x10FFFF``  

     

    Any characters not included in this list will be rejected. For more information, see the `W3C specification for characters <http://www.w3.org/TR/REC-xml/#charsets>`_ .

     

  

``--delay-seconds`` (integer)


  The length of time, in seconds, for which to delay a specific message. Valid values: 0 to 900. Maximum: 15 minutes. Messages with a positive ``DelaySeconds`` value become available for processing after the delay period is finished. If you don't specify a value, the default value for the queue applies. 

   

  .. note::

     

    When you set ``FifoQueue`` , you can't set ``DelaySeconds`` per message. You can set this parameter only on a queue level.

     

  

``--message-attributes`` (map)


  Each message attribute consists of a ``Name`` , ``Type`` , and ``Value`` . For more information, see `Message Attribute Items and Validation <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-message-attributes.html#message-attributes-items-validation>`_ in the *Amazon SQS Developer Guide* .

  



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



``--message-deduplication-id`` (string)


  This parameter applies only to FIFO (first-in-first-out) queues.

   

  The token used for deduplication of sent messages. If a message with a particular ``MessageDeduplicationId`` is sent successfully, any messages sent with the same ``MessageDeduplicationId`` are accepted successfully but aren't delivered during the 5-minute deduplication interval. For more information, see `Exactly-Once Processing <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html#FIFO-queues-exactly-once-processing>`_ in the *Amazon SQS Developer Guide* .

   

   
  * Every message must have a unique ``MessageDeduplicationId`` , 

     
    * You may provide a ``MessageDeduplicationId`` explicitly. 
     
    * If you aren't able to provide a ``MessageDeduplicationId`` and you enable ``ContentBasedDeduplication`` for your queue, Amazon SQS uses a SHA-256 hash to generate the ``MessageDeduplicationId`` using the body of the message (but not the attributes of the message).  
     
    * If you don't provide a ``MessageDeduplicationId`` and the queue doesn't have ``ContentBasedDeduplication`` set, the action fails with an error. 
     
    * If the queue has ``ContentBasedDeduplication`` set, your ``MessageDeduplicationId`` overrides the generated one. 
     

   
   
  * When ``ContentBasedDeduplication`` is in effect, messages with identical content sent within the deduplication interval are treated as duplicates and only one copy of the message is delivered. 
   
  * If you send one message with ``ContentBasedDeduplication`` enabled and then another message with a ``MessageDeduplicationId`` that is the same as the one generated for the first ``MessageDeduplicationId`` , the two messages are treated as duplicates and only one copy of the message is delivered.  
   

   

  .. note::

     

    The ``MessageDeduplicationId`` is available to the recipient of the message (this can be useful for troubleshooting delivery issues).

     

    If a message is sent successfully but the acknowledgement is lost and the message is resent with the same ``MessageDeduplicationId`` after the deduplication interval, Amazon SQS can't detect duplicate messages.

     

   

  The length of ``MessageDeduplicationId`` is 128 characters. ``MessageDeduplicationId`` can contain alphanumeric characters (``a-z`` , ``A-Z`` , ``0-9`` ) and punctuation (``!"#$%'()*+,-./:;=?@[\]^_`{|}~`` ).

   

  For best practices of using ``MessageDeduplicationId`` , see `Using the MessageDeduplicationId Property <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queue-recommendations.html#using-messagededuplicationid-property>`_ in the *Amazon Simple Queue Service Developer Guide* .

  

``--message-group-id`` (string)


  This parameter applies only to FIFO (first-in-first-out) queues.

   

  The tag that specifies that a message belongs to a specific message group. Messages that belong to the same message group are processed in a FIFO manner (however, messages in different message groups might be processed out of order). To interleave multiple ordered streams within a single queue, use ``MessageGroupId`` values (for example, session data for multiple users). In this scenario, multiple readers can process the queue, but the session data of each user is processed in a FIFO fashion.

   

   
  * You must associate a non-empty ``MessageGroupId`` with a message. If you don't provide a ``MessageGroupId`` , the action fails. 
   
  * ``receive-message`` might return messages with multiple ``MessageGroupId`` values. For each ``MessageGroupId`` , the messages are sorted by time sent. The caller can't specify a ``MessageGroupId`` . 
   

   

  The length of ``MessageGroupId`` is 128 characters. Valid values are alphanumeric characters and punctuation ``(!"#$%'()*+,-./:;=?@[\]^_`{|}~)`` .

   

  For best practices of using ``MessageGroupId`` , see `Using the MessageGroupId Property <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queue-recommendations.html#using-messagegroupid-property>`_ in the *Amazon Simple Queue Service Developer Guide* .

   

  .. warning::

     

     ``MessageGroupId`` is required for FIFO queues. You can't use it for Standard queues.

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  An MD5 digest of the non-URL-encoded message attribute string. You can use this attribute to verify that Amazon SQS received the message correctly. Amazon SQS URL-decodes the message before creating the MD5 digest. For information about MD5, see `RFC1321 <https://www.ietf.org/rfc/rfc1321.txt>`_ .

  

  

MD5OfMessageAttributes -> (string)

  

  An MD5 digest of the non-URL-encoded message attribute string. You can use this attribute to verify that Amazon SQS received the message correctly. Amazon SQS URL-decodes the message before creating the MD5 digest. For information about MD5, see `RFC1321 <https://www.ietf.org/rfc/rfc1321.txt>`_ .

  

  

MessageId -> (string)

  

  An attribute containing the ``MessageId`` of the message sent to the queue. For more information, see `Queue and Message Identifiers <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-queue-message-identifiers.html>`_ in the *Amazon SQS Developer Guide* . 

  

  

SequenceNumber -> (string)

  

  This parameter applies only to FIFO (first-in-first-out) queues.

   

  The large, non-consecutive number that Amazon SQS assigns to each message.

   

  The length of ``SequenceNumber`` is 128 bits. ``SequenceNumber`` continues to increase for a particular ``MessageGroupId`` .

  

  

