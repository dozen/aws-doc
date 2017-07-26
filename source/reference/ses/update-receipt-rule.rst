[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses update-receipt-rule:


*******************
update-receipt-rule
*******************



===========
Description
===========



Updates a receipt rule.

 

For information about managing receipt rules, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-managing-receipt-rules.html>`_ .

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/UpdateReceiptRule>`_


========
Synopsis
========

::

    update-receipt-rule
  --rule-set-name <value>
  --rule <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule-set-name`` (string)


  The name of the receipt rule set to which the receipt rule belongs.

  

``--rule`` (structure)


  A data structure that contains the updated receipt rule information.

  



JSON Syntax::

  {
    "Name": "string",
    "Enabled": true|false,
    "TlsPolicy": "Require"|"Optional",
    "Recipients": ["string", ...],
    "Actions": [
      {
        "S3Action": {
          "TopicArn": "string",
          "BucketName": "string",
          "ObjectKeyPrefix": "string",
          "KmsKeyArn": "string"
        },
        "BounceAction": {
          "TopicArn": "string",
          "SmtpReplyCode": "string",
          "StatusCode": "string",
          "Message": "string",
          "Sender": "string"
        },
        "WorkmailAction": {
          "TopicArn": "string",
          "OrganizationArn": "string"
        },
        "LambdaAction": {
          "TopicArn": "string",
          "FunctionArn": "string",
          "InvocationType": "Event"|"RequestResponse"
        },
        "StopAction": {
          "Scope": "RuleSet",
          "TopicArn": "string"
        },
        "AddHeaderAction": {
          "HeaderName": "string",
          "HeaderValue": "string"
        },
        "SNSAction": {
          "TopicArn": "string",
          "Encoding": "UTF-8"|"Base64"
        }
      }
      ...
    ],
    "ScanEnabled": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

