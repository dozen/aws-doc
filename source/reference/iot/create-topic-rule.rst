[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-topic-rule:


*****************
create-topic-rule
*****************



===========
Description
===========



Creates a rule.



========
Synopsis
========

::

    create-topic-rule
  --rule-name <value>
  --topic-rule-payload <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rule-name`` (string)


  The name of the rule.

  

``--topic-rule-payload`` (structure)


  The rule payload.

  



JSON Syntax::

  {
    "sql": "string",
    "description": "string",
    "actions": [
      {
        "dynamoDB": {
          "tableName": "string",
          "roleArn": "string",
          "hashKeyField": "string",
          "hashKeyValue": "string",
          "rangeKeyField": "string",
          "rangeKeyValue": "string",
          "payloadField": "string"
        },
        "lambda": {
          "functionArn": "string"
        },
        "sns": {
          "targetArn": "string",
          "roleArn": "string"
        },
        "sqs": {
          "roleArn": "string",
          "queueUrl": "string",
          "useBase64": true|false
        },
        "kinesis": {
          "roleArn": "string",
          "streamName": "string",
          "partitionKey": "string"
        },
        "republish": {
          "roleArn": "string",
          "topic": "string"
        },
        "s3": {
          "roleArn": "string",
          "bucketName": "string",
          "key": "string"
        },
        "firehose": {
          "roleArn": "string",
          "deliveryStreamName": "string"
        }
      }
      ...
    ],
    "ruleDisabled": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None