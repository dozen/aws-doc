[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses update-receipt-rule:


*******************
update-receipt-rule
*******************



===========
Description
===========



Updates a receipt rule.

 

For information about managing receipt rules, see the `Amazon SES Developer Guide`_ .

 

This action is throttled at one request per second.



========
Synopsis
========

::

    update-receipt-rule
  --rule-set-name <value>
  --rule <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======



.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-managing-receipt-rules.html
