[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot get-topic-rule:


**************
get-topic-rule
**************



===========
Description
===========



Gets information about the specified rule.



========
Synopsis
========

::

    get-topic-rule
  --rule-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rule-name`` (string)


  The name of the rule.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ruleArn -> (string)

  

  The rule ARN.

  

  

rule -> (structure)

  

  The rule.

  

  ruleName -> (string)

    

    The name of the rule.

    

    

  sql -> (string)

    

    The SQL statement used to query the topic. When using a SQL query with multiple lines, be sure to escape the newline characters properly.

    

    

  description -> (string)

    

    The description of the rule.

    

    

  createdAt -> (timestamp)

    

    The date and time the rule was created.

    

    

  actions -> (list)

    

    The actions associated with the rule.

    

    (structure)

      

      Describes the actions associated with a rule.

      

      dynamoDB -> (structure)

        

        Write to a DynamoDB table.

        

        tableName -> (string)

          

          The name of the DynamoDB table.

          

          

        roleArn -> (string)

          

          The ARN of the IAM role that grants access to the DynamoDB table.

          

          

        hashKeyField -> (string)

          

          The hash key name.

          

          

        hashKeyValue -> (string)

          

          The hash key value.

          

          

        rangeKeyField -> (string)

          

          The range key name.

          

          

        rangeKeyValue -> (string)

          

          The range key value.

          

          

        payloadField -> (string)

          

          The action payload, this name can be customized.

          

          

        

      lambda -> (structure)

        

        Invoke a Lambda function.

        

        functionArn -> (string)

          

          The ARN of the Lambda function.

          

          

        

      sns -> (structure)

        

        Publish to an SNS topic.

        

        targetArn -> (string)

          

          The ARN of the SNS topic.

          

          

        roleArn -> (string)

          

          The ARN of the IAM role that grants access.

          

          

        

      sqs -> (structure)

        

        Publish to an SQS queue.

        

        roleArn -> (string)

          

          The ARN of the IAM role that grants access.

          

          

        queueUrl -> (string)

          

          The URL of the Amazon SQS queue.

          

          

        useBase64 -> (boolean)

          

          Specifies whether to use Base64 encoding.

          

          

        

      kinesis -> (structure)

        

        Write data to a Kinesis stream.

        

        roleArn -> (string)

          

          The ARN of the IAM role that grants access to the Kinesis stream.

          

          

        streamName -> (string)

          

          The name of the Kinesis stream.

          

          

        partitionKey -> (string)

          

          The partition key.

          

          

        

      republish -> (structure)

        

        Publish to another MQTT topic.

        

        roleArn -> (string)

          

          The ARN of the IAM role that grants access.

          

          

        topic -> (string)

          

          The name of the MQTT topic.

          

          

        

      s3 -> (structure)

        

        Write to an S3 bucket.

        

        roleArn -> (string)

          

          The ARN of the IAM role that grants access.

          

          

        bucketName -> (string)

          

          The S3 bucket.

          

          

        key -> (string)

          

          The object key.

          

          

        

      firehose -> (structure)

        

        Write to a Kinesis Firehose stream.

        

        roleArn -> (string)

          

          The IAM role that grants access to the firehose stream.

          

          

        deliveryStreamName -> (string)

          

          The delivery stream name.

          

          

        

      

    

  ruleDisabled -> (boolean)

    

    Specifies whether the rule is disabled.

    

    

  

