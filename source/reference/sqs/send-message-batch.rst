[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs send-message-batch:


******************
send-message-batch
******************



===========
Description
===========



Delivers up to ten messages to the specified queue. This is a batch version of  send-message . The result of the send action on each message is reported individually in the response. The maximum allowed individual message size is 256 KB (262,144 bytes).

 

The maximum total payload size (i.e., the sum of all a batch's individual message lengths) is also 256 KB (262,144 bytes).

 

If the ``DelaySeconds`` parameter is not specified for an entry, the default for the queue is used.

 

.. warning::

  The following list shows the characters (in Unicode) that are allowed in your message, according to the W3C XML specification. For more information, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ . If you send any characters that are not included in the list, your request will be rejected. 

  #x9 | #xA | #xD | [#x20 to #xD7FF] | [#xE000 to #xFFFD] | [#x10000 to #x10FFFF]

   

 

.. warning::

  Because the batch request can result in a combination of successful and unsuccessful actions, you should check for batch errors even when the call returns an HTTP status code of 200. 

 

.. note::

  Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this: 

 

``Attribute.1=this`` 

 

``Attribute.2=that`` 



========
Synopsis
========

::

    send-message-batch
  --queue-url <value>
  --entries <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to take action on.

  

``--entries`` (list)


  A list of  SendMessageBatchRequestEntry items.

  



Shorthand Syntax::

    Id=string,MessageBody=string,DelaySeconds=integer,MessageAttributes={KeyName1={StringValue=string,BinaryValue=blob,StringListValues=[string,string],BinaryListValues=[blob,blob],DataType=string},KeyName2={StringValue=string,BinaryValue=blob,StringListValues=[string,string],BinaryListValues=[blob,blob],DataType=string}} ...




JSON Syntax::

  [
    {
      "Id": "string",
      "MessageBody": "string",
      "DelaySeconds": integer,
      "MessageAttributes": {"string": {
            "StringValue": "string",
            "BinaryValue": blob,
            "StringListValues": ["string", ...],
            "BinaryListValues": [blob, ...],
            "DataType": "string"
          }
        ...}
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To send multiple messages as a batch**

This example sends 2 messages with the specified message bodies, delay periods, and message attributes, to the specified queue.

Command::

  aws sqs send-message-batch --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue --entries file://send-message-batch.json 
  
Input file (send-message-batch.json)::

  [
    {
      "Id": "FuelReport-0001-2015-09-16T140731Z",
	  "MessageBody": "Fuel report for account 0001 on 2015-09-16 at 02:07:31 PM.",
	  "DelaySeconds": 10,
	  "MessageAttributes": {
	    "SellerName": {
	      "DataType": "String",
		  "StringValue": "Example Store"
        },
	    "City": {
          "DataType": "String",
          "StringValue": "Any City"
        },
	    "Region": {
	      "DataType": "String", 
		  "StringValue": "WA"
        },
	    "PostalCode": {
	      "DataType": "String",
		  "StringValue": "99065"
	    },
	    "PricePerGallon": {
	      "DataType": "Number",
		  "StringValue": "1.99"
        }
	  }
    },
    {
      "Id": "FuelReport-0002-2015-09-16T140930Z",
	  "MessageBody": "Fuel report for account 0002 on 2015-09-16 at 02:09:30 PM.",
	  "DelaySeconds": 10,
	  "MessageAttributes": {
	    "SellerName": {
	      "DataType": "String",
		  "StringValue": "Example Fuels"
        },
	    "City": {
          "DataType": "String",
          "StringValue": "North Town"
        },
	    "Region": {
	      "DataType": "String", 
		  "StringValue": "WA"
        },
	    "PostalCode": {
	      "DataType": "String",
		  "StringValue": "99123"
	    },
	    "PricePerGallon": {
	      "DataType": "Number",
		  "StringValue": "1.87"
        }
	  }
    }
  ]

Output::

  {
    "Successful": [
      {
        "MD5OfMessageBody": "203c4a38...7943237e",
        "MD5OfMessageAttributes": "10809b55...baf283ef",
        "Id": "FuelReport-0001-2015-09-16T140731Z",
        "MessageId": "d175070c-d6b8-4101-861d-adeb3EXAMPLE"
      },
      {
        "MD5OfMessageBody": "2cf0159a...c1980595",
        "MD5OfMessageAttributes": "55623928...ae354a25",
        "Id": "FuelReport-0002-2015-09-16T140930Z",
        "MessageId": "f9b7d55d-0570-413e-b9c5-a9264EXAMPLE"
      }
    ]
  }

  
	

======
Output
======

Successful -> (list)

  

  A list of  SendMessageBatchResultEntry items.

  

  (structure)

    

    Encloses a message ID for successfully enqueued message of a  send-message-batch .

    

    Id -> (string)

      

      An identifier for the message in this batch.

      

      

    MessageId -> (string)

      

      An identifier for the message.

      

      

    MD5OfMessageBody -> (string)

      

      An MD5 digest of the non-URL-encoded message body string. This can be used to verify that Amazon SQS received the message correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

      

      

    MD5OfMessageAttributes -> (string)

      

      An MD5 digest of the non-URL-encoded message attribute string. This can be used to verify that Amazon SQS received the message batch correctly. Amazon SQS first URL decodes the message before creating the MD5 digest. For information about MD5, go to `http\://www.faqs.org/rfcs/rfc1321.html`_ .

      

      

    

  

Failed -> (list)

  

  A list of  BatchResultErrorEntry items with the error detail about each message that could not be enqueued.

  

  (structure)

    

    This is used in the responses of batch API to give a detailed description of the result of an action on each entry in the request.

    

    Id -> (string)

      

      The id of an entry in a batch request.

      

      

    SenderFault -> (boolean)

      

      Whether the error happened due to the sender's fault.

      

      

    Code -> (string)

      

      An error code representing why the action failed on this entry.

      

      

    Message -> (string)

      

      A message explaining why the action failed on this entry.

      

      

    

  



.. _http\://www.faqs.org/rfcs/rfc1321.html: http://www.faqs.org/rfcs/rfc1321.html
