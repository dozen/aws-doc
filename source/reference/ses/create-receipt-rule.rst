[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses create-receipt-rule:


*******************
create-receipt-rule
*******************



===========
Description
===========



Creates a receipt rule.

 

For information about setting up receipt rules, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-receipt-rules.html>`_ .

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/CreateReceiptRule>`_


========
Synopsis
========

::

    create-receipt-rule
  --rule-set-name <value>
  [--after <value>]
  --rule <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule-set-name`` (string)


  The name of the rule set to which to add the rule.

  

``--after`` (string)


  The name of an existing rule after which the new rule will be placed. If this parameter is null, the new rule will be inserted at the beginning of the rule list.

  

``--rule`` (structure)


  A data structure that contains the specified rule's name, actions, recipients, domains, enabled status, scan status, and TLS policy.

  



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

