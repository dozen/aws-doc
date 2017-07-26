[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses send-bounce:


***********
send-bounce
***********



===========
Description
===========



Generates and sends a bounce message to the sender of an email you received through Amazon SES. You can only use this API on an email up to 24 hours after you receive it.

 

.. note::

   

  You cannot use this API to send generic bounces for mail that was not received by Amazon SES.

   

 

For information about receiving email through Amazon SES, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email.html>`_ .

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/SendBounce>`_


========
Synopsis
========

::

    send-bounce
  --original-message-id <value>
  --bounce-sender <value>
  [--explanation <value>]
  [--message-dsn <value>]
  --bounced-recipient-info-list <value>
  [--bounce-sender-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--original-message-id`` (string)


  The message ID of the message to be bounced.

  

``--bounce-sender`` (string)


  The address to use in the "From" header of the bounce message. This must be an identity that you have verified with Amazon SES.

  

``--explanation`` (string)


  Human-readable text for the bounce message to explain the failure. If not specified, the text will be auto-generated based on the bounced recipient information.

  

``--message-dsn`` (structure)


  Message-related DSN fields. If not specified, Amazon SES will choose the values.

  



Shorthand Syntax::

    ReportingMta=string,ArrivalDate=timestamp,ExtensionFields=[{Name=string,Value=string},{Name=string,Value=string}]




JSON Syntax::

  {
    "ReportingMta": "string",
    "ArrivalDate": timestamp,
    "ExtensionFields": [
      {
        "Name": "string",
        "Value": "string"
      }
      ...
    ]
  }



``--bounced-recipient-info-list`` (list)


  A list of recipients of the bounced message, including the information required to create the Delivery Status Notifications (DSNs) for the recipients. You must specify at least one ``BouncedRecipientInfo`` in the list.

  



JSON Syntax::

  [
    {
      "Recipient": "string",
      "RecipientArn": "string",
      "BounceType": "DoesNotExist"|"MessageTooLarge"|"ExceededQuota"|"ContentRejected"|"Undefined"|"TemporaryFailure",
      "RecipientDsnFields": {
        "FinalRecipient": "string",
        "Action": "failed"|"delayed"|"delivered"|"relayed"|"expanded",
        "RemoteMta": "string",
        "Status": "string",
        "DiagnosticCode": "string",
        "LastAttemptDate": timestamp,
        "ExtensionFields": [
          {
            "Name": "string",
            "Value": "string"
          }
          ...
        ]
      }
    }
    ...
  ]



``--bounce-sender-arn`` (string)


  This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to use the address in the "From" header of the bounce. For more information about sending authorization, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/sending-authorization.html>`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

MessageId -> (string)

  

  The message ID of the bounce message.

  

  

