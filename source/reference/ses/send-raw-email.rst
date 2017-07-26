[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses send-raw-email:


**************
send-raw-email
**************



===========
Description
===========



Sends an email message, with header and content specified by the client. The ``send-raw-email`` action is useful for sending multipart MIME emails. The raw text of the message must comply with Internet email standards; otherwise, the message cannot be sent. 

 

There are several important points to know about ``send-raw-email`` :

 

 
* You can only send email from verified email addresses and domains; otherwise, you will get an "Email address not verified" error. If your account is still in the Amazon SES sandbox, you must also verify every recipient email address except for the recipients provided by the Amazon SES mailbox simulator. For more information, go to the `Amazon SES Developer Guide`_ .
 
* The total size of the message cannot exceed 10 MB. This includes any attachments that are part of the message.
 
* Amazon SES has a limit on the total number of recipients per message. The combined number of To:, CC: and BCC: email addresses cannot exceed 50. If you need to send an email message to a larger audience, you can divide your recipient list into groups of 50 or fewer, and then call Amazon SES repeatedly to send the message to each group.
 
* The To:, CC:, and BCC: headers in the raw message can contain a group list. Note that each recipient in a group list counts towards the 50-recipient limit.
 
* For every message that you send, the total number of recipients (To:, CC: and BCC:) is counted against your sending quota - the maximum number of emails you can send in a 24-hour period. For information about your sending quota, go to the `Amazon SES Developer Guide`_ .
 
* If you are using sending authorization to send on behalf of another user, ``send-raw-email`` enables you to specify the cross-account identity for the email's "Source," "From," and "Return-Path" parameters in one of two ways: you can pass optional parameters ``SourceArn`` , ``FromArn`` , and/or ``ReturnPathArn`` to the API, or you can include the following X-headers in the header of your raw email: 

   
  * ``X-SES-SOURCE-ARN`` 
   
  * ``X-SES-FROM-ARN`` 
   
  * ``X-SES-RETURN-PATH-ARN`` 
   

 

.. warning::

  Do not include these X-headers in the DKIM signature, because they are removed by Amazon SES before sending the email.

For the most common sending authorization use case, we recommend that you specify the ``SourceIdentityArn`` and do not specify either the ``FromIdentityArn`` or ``ReturnPathIdentityArn`` . (The same note applies to the corresponding X-headers.) If you only specify the ``SourceIdentityArn`` , Amazon SES will simply set the "From" address and the "Return Path" address to the identity specified in ``SourceIdentityArn`` . For more information about sending authorization, see the `Amazon SES Developer Guide`_ .
 



========
Synopsis
========

::

    send-raw-email
  [--source <value>]
  [--destinations <value>]
  --raw-message <value>
  [--from-arn <value>]
  [--source-arn <value>]
  [--return-path-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--source`` (string)


  The identity's email address. If you do not provide a value for this parameter, you must specify a "From" address in the raw text of the message. (You can also specify both.)

   

  By default, the string must be 7-bit ASCII. If the text must contain any other characters, then you must use MIME encoded-word syntax (RFC 2047) instead of a literal string. MIME encoded-word syntax uses the following form: ``=?charset?encoding?encoded-text?=`` . For more information, see `RFC 2047`_ . 

   

  .. note::

    If you specify the ``Source`` parameter and have feedback forwarding enabled, then bounces and complaints will be sent to this email address. This takes precedence over any *Return-Path* header that you might include in the raw text of the message. 

  

``--destinations`` (list)


  A list of destinations for the message, consisting of To:, CC:, and BCC: addresses.

  



Syntax::

  "string" "string" ...



``--raw-message`` (structure)


  The raw text of the message. The client is responsible for ensuring the following:

   

   

   
  * Message must contain a header and a body, separated by a blank line.
   
  * All required header fields must be present.
   
  * Each part of a multipart MIME message must be formatted properly.
   
  * MIME content types must be among those supported by Amazon SES. For more information, go to the `Amazon SES Developer Guide`_ . 
   
  * Content must be base64-encoded, if MIME requires it.
   

   

  



Shorthand Syntax::

    Data=blob




JSON Syntax::

  {
    "Data": blob
  }



``--from-arn`` (string)


  This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to specify a particular "From" address in the header of the raw email.

   

  Instead of using this parameter, you can use the X-header ``X-SES-FROM-ARN`` in the raw message of the email. If you use both the ``FromArn`` parameter and the corresponding X-header, Amazon SES uses the value of the ``FromArn`` parameter.

   

  .. note::

    For information about when to use this parameter, see the description of ``send-raw-email`` in this guide, or see the `Amazon SES Developer Guide`_ . 

  

``--source-arn`` (string)


  This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to send for the email address specified in the ``Source`` parameter.

   

  For example, if the owner of ``example.com`` (which has ARN ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` ) attaches a policy to it that authorizes you to send from ``user@example.com`` , then you would specify the ``SourceArn`` to be ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` , and the ``Source`` to be ``user@example.com`` .

   

  Instead of using this parameter, you can use the X-header ``X-SES-SOURCE-ARN`` in the raw message of the email. If you use both the ``SourceArn`` parameter and the corresponding X-header, Amazon SES uses the value of the ``SourceArn`` parameter.

   

  .. note::

    For information about when to use this parameter, see the description of ``send-raw-email`` in this guide, or see the `Amazon SES Developer Guide`_ . 

  

``--return-path-arn`` (string)


  This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to use the email address specified in the ``ReturnPath`` parameter.

   

  For example, if the owner of ``example.com`` (which has ARN ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` ) attaches a policy to it that authorizes you to use ``feedback@example.com`` , then you would specify the ``ReturnPathArn`` to be ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` , and the ``ReturnPath`` to be ``feedback@example.com`` .

   

  Instead of using this parameter, you can use the X-header ``X-SES-RETURN-PATH-ARN`` in the raw message of the email. If you use both the ``ReturnPathArn`` parameter and the corresponding X-header, Amazon SES uses the value of the ``ReturnPathArn`` parameter.

   

  .. note::

    For information about when to use this parameter, see the description of ``send-raw-email`` in this guide, or see the `Amazon SES Developer Guide`_ . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To send a raw email using Amazon SES**

The following example uses the ``send-raw-email`` command to send an email with a TXT attachment::

    aws ses send-raw-email --raw-message file://c:\temp\message.json

Output::

 {
    "MessageId": "EXAMPLEf3f73d99b-c63fb06f-d263-41f8-a0fb-d0dc67d56c07-000000"
 }

The raw message is a JSON data structure saved in the message.json file. It contains the following::

 {
    "Data": "From: sender@example.com\nTo: recipient@example.com\nSubject: Test email sent using the AWS CLI (contains an attachment)\nMIME-Version: 1.0\nContent-type: Multipart/Mixed; boundary=\"NextPart\"\n\n--NextPart\nContent-Type: text/plain\n\nThis is the message body.\n\n--NextPart\nContent-Type: text/plain;\nContent-Disposition: attachment; filename=\"attachment.txt\"\n\nThis is the text in the attachment.\n\n--NextPart--"
 }

As you can see, "Data" is one long string that contains the entire raw email content in MIME format, including an attachment called attachment.txt.

Replace sender@example.com and recipient@example.com with the addresses you want to use. Note that the sender's email address must be verified with Amazon SES. Until you are granted production access to Amazon SES, you must also verify the email address of the recipient
unless the recipient is the Amazon SES mailbox simulator. For more information on verification, see `Verifying Email Addresses and Domains in Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

The Message ID in the output indicates that the call to send-raw-email was successful.

If you don't receive the email, check your Junk box.

For more information on sending raw email, see `Sending Raw Email Using the Amazon SES API`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Sending Raw Email Using the Amazon SES API`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/send-email-raw.html
.. _`Verifying Email Addresses and Domains in Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/verify-addresses-and-domains.html



======
Output
======

MessageId -> (string)

  

  The unique message identifier returned from the ``send-raw-email`` action. 

  

  



.. _RFC 2047: http://tools.ietf.org/html/rfc2047
.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/sending-authorization-delegate-sender-tasks-email.html
