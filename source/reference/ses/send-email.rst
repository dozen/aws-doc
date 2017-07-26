[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses send-email:


**********
send-email
**********



===========
Description
===========



Composes an email message based on input data, and then immediately queues the message for sending. 

 

There are several important points to know about ``send-email`` :

 

 
* You can only send email from verified email addresses and domains; otherwise, you will get an "Email address not verified" error. If your account is still in the Amazon SES sandbox, you must also verify every recipient email address except for the recipients provided by the Amazon SES mailbox simulator. For more information, go to the `Amazon SES Developer Guide`_ .
 
* The total size of the message cannot exceed 10 MB. This includes any attachments that are part of the message.
 
* Amazon SES has a limit on the total number of recipients per message. The combined number of To:, CC: and BCC: email addresses cannot exceed 50. If you need to send an email message to a larger audience, you can divide your recipient list into groups of 50 or fewer, and then call Amazon SES repeatedly to send the message to each group.
 
* For every message that you send, the total number of recipients (To:, CC: and BCC:) is counted against your sending quota - the maximum number of emails you can send in a 24-hour period. For information about your sending quota, go to the `Amazon SES Developer Guide`_ .
 



========
Synopsis
========

::

    send-email
  [--destination <value>]
  [--message <value>]
  [--reply-to-addresses <value>]
  [--return-path <value>]
  [--source-arn <value>]
  [--return-path-arn <value>]
  --from <value>
  [--to <value>]
  [--cc <value>]
  [--bcc <value>]
  [--subject <value>]
  [--text <value>]
  [--html <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--destination`` (structure)


  The destination for this email, composed of To:, CC:, and BCC: fields.

  



Shorthand Syntax::

    ToAddresses=string,string,CcAddresses=string,string,BccAddresses=string,string




JSON Syntax::

  {
    "ToAddresses": ["string", ...],
    "CcAddresses": ["string", ...],
    "BccAddresses": ["string", ...]
  }



``--message`` (structure)


  The message to be sent.

  



Shorthand Syntax::

    Subject={Data=string,Charset=string},Body={Text={Data=string,Charset=string},Html={Data=string,Charset=string}}




JSON Syntax::

  {
    "Subject": {
      "Data": "string",
      "Charset": "string"
    },
    "Body": {
      "Text": {
        "Data": "string",
        "Charset": "string"
      },
      "Html": {
        "Data": "string",
        "Charset": "string"
      }
    }
  }



``--reply-to-addresses`` (list)


  The reply-to email address(es) for the message. If the recipient replies to the message, each reply-to address will receive the reply. 

  



Syntax::

  "string" "string" ...



``--return-path`` (string)


  The email address to which bounces and complaints are to be forwarded when feedback forwarding is enabled. If the message cannot be delivered to the recipient, then an error message will be returned from the recipient's ISP; this message will then be forwarded to the email address specified by the ``ReturnPath`` parameter. The ``ReturnPath`` parameter is never overwritten. This email address must be either individually verified with Amazon SES, or from a domain that has been verified with Amazon SES. 

  

``--source-arn`` (string)


  This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to send for the email address specified in the ``Source`` parameter.

   

  For example, if the owner of ``example.com`` (which has ARN ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` ) attaches a policy to it that authorizes you to send from ``user@example.com`` , then you would specify the ``SourceArn`` to be ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` , and the ``Source`` to be ``user@example.com`` .

   

  For more information about sending authorization, see the `Amazon SES Developer Guide`_ . 

  

``--return-path-arn`` (string)


  This parameter is used only for sending authorization. It is the ARN of the identity that is associated with the sending authorization policy that permits you to use the email address specified in the ``ReturnPath`` parameter.

   

  For example, if the owner of ``example.com`` (which has ARN ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` ) attaches a policy to it that authorizes you to use ``feedback@example.com`` , then you would specify the ``ReturnPathArn`` to be ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` , and the ``ReturnPath`` to be ``feedback@example.com`` .

   

  For more information about sending authorization, see the `Amazon SES Developer Guide`_ . 

  

``--from`` (string)


  The email address that is sending the email. This email address must be either individually verified with Amazon SES, or from a domain that has been verified with Amazon SES. For information about verifying identities, see the `Amazon SES Developer Guide`_ .

   

  If you are sending on behalf of another user and have been permitted to do so by a sending authorization policy, then you must also specify the ``SourceArn`` parameter. For more information about sending authorization, see the `Amazon SES Developer Guide`_ .

   

  In all cases, the email address must be 7-bit ASCII. If the text must contain any other characters, then you must use MIME encoded-word syntax (RFC 2047) instead of a literal string. MIME encoded-word syntax uses the following form: ``=?charset?encoding?encoded-text?=`` . For more information, see `RFC 2047`_ . 

  

``--to`` (string)
The email addresses of the primary recipients. You can specify multiple recipients as space-separated values

``--cc`` (string)
The email addresses of copy recipients (Cc). You can specify multiple recipients as space-separated values

``--bcc`` (string)
The email addresses of blind-carbon-copy recipients (Bcc). You can specify multiple recipients as space-separated values

``--subject`` (string)
The subject of the message

``--text`` (string)
The raw text body of the message

``--html`` (string)
The HTML body of the message

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To send a formatted email using Amazon SES**

The following example uses the ``send-email`` command to send a formatted email::

    aws ses send-email --from sender@example.com --destination file://c:\temp\destination.json --message file://c:\temp\message.json

Output::

 {
    "MessageId": "EXAMPLEf3a5efcd1-51adec81-d2a4-4e3f-9fe2-5d85c1b23783-000000"
 }

The destination and the message are JSON data structures saved in .json files in a directory called c:\\temp. These files are as follows:

``destination.json``::

 {
   "ToAddresses":  ["recipient1@example.com", "recipient2@example.com"],
   "CcAddresses":  ["recipient3@example.com"],
   "BccAddresses": []
 }

``message.json``::

 {
    "Subject": {
        "Data": "Test email sent using the AWS CLI",
        "Charset": "UTF-8"
    },
    "Body": {
        "Text": {
            "Data": "This is the message body in text format.",
            "Charset": "UTF-8"
        },
        "Html": {
            "Data": "This message body contains HTML formatting. It can, for example, contain links like this one: <a class=\"ulink\" href=\"http://docs.aws.amazon.com/ses/latest/DeveloperGuide\" target=\"_blank\">Amazon SES Developer Guide</a>.",
            "Charset": "UTF-8"
        }
    }
 }

Replace the sender and recipient email addresses with the ones you want to use. Note that the sender's email address must be verified with Amazon SES. Until you are granted production access to Amazon SES, you must also verify the email address of each recipient
unless the recipient is the Amazon SES mailbox simulator. For more information on verification, see `Verifying Email Addresses and Domains in Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

The Message ID in the output indicates that the call to send-email was successful.

If you don't receive the email, check your Junk box.

For more information on sending formatted email, see `Sending Formatted Email Using the Amazon SES API`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Verifying Email Addresses and Domains in Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/verify-addresses-and-domains.html
.. _`Sending Formatted Email Using the Amazon SES API`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/send-email-formatted.html


======
Output
======

MessageId -> (string)

  

  The unique message identifier returned from the ``send-email`` action. 

  

  



.. _RFC 2047: http://tools.ietf.org/html/rfc2047
.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/sending-authorization.html
