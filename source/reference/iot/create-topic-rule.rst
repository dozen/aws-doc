[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-topic-rule:


*****************
create-topic-rule
*****************



===========
Description
===========



Creates a rule. Creating rules is an administrator-level action. Any user who has permission to create rules will be able to access data processed by the rule.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/CreateTopicRule>`_


========
Synopsis
========

::

    create-topic-rule
  --rule-name <value>
  --topic-rule-payload <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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
          "operation": "string",
          "hashKeyField": "string",
          "hashKeyValue": "string",
          "hashKeyType": "STRING"|"NUMBER",
          "rangeKeyField": "string",
          "rangeKeyValue": "string",
          "rangeKeyType": "STRING"|"NUMBER",
          "payloadField": "string"
        },
        "dynamoDBv2": {
          "roleArn": "string",
          "putItem": {
            "tableName": "string"
          }
        },
        "lambda": {
          "functionArn": "string"
        },
        "sns": {
          "targetArn": "string",
          "roleArn": "string",
          "messageFormat": "RAW"|"JSON"
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
          "key": "string",
          "cannedAcl": "private"|"public-read"|"public-read-write"|"aws-exec-read"|"authenticated-read"|"bucket-owner-read"|"bucket-owner-full-control"|"log-delivery-write"
        },
        "firehose": {
          "roleArn": "string",
          "deliveryStreamName": "string",
          "separator": "string"
        },
        "cloudwatchMetric": {
          "roleArn": "string",
          "metricNamespace": "string",
          "metricName": "string",
          "metricValue": "string",
          "metricUnit": "string",
          "metricTimestamp": "string"
        },
        "cloudwatchAlarm": {
          "roleArn": "string",
          "alarmName": "string",
          "stateReason": "string",
          "stateValue": "string"
        },
        "elasticsearch": {
          "roleArn": "string",
          "endpoint": "string",
          "index": "string",
          "type": "string",
          "id": "string"
        },
        "salesforce": {
          "token": "string",
          "url": "string"
        }
      }
      ...
    ],
    "ruleDisabled": true|false,
    "awsIotSqlVersion": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None