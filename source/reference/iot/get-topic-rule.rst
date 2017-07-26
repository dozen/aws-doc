[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot get-topic-rule:


**************
get-topic-rule
**************



===========
Description
===========



Gets information about the specified rule.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/GetTopicRule>`_


========
Synopsis
========

::

    get-topic-rule
  --rule-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule-name`` (string)


  The name of the rule.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    The SQL statement used to query the topic. When using a SQL query with multiple lines, be sure to escape the newline characters.

    

    

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

          

          

        operation -> (string)

          

          The type of operation to be performed. This follows the substitution template, so it can be ``${operation}`` , but the substitution must result in one of the following: ``INSERT`` , ``UPDATE`` , or ``DELETE`` .

          

          

        hashKeyField -> (string)

          

          The hash key name.

          

          

        hashKeyValue -> (string)

          

          The hash key value.

          

          

        hashKeyType -> (string)

          

          The hash key type. Valid values are "STRING" or "NUMBER"

          

          

        rangeKeyField -> (string)

          

          The range key name.

          

          

        rangeKeyValue -> (string)

          

          The range key value.

          

          

        rangeKeyType -> (string)

          

          The range key type. Valid values are "STRING" or "NUMBER"

          

          

        payloadField -> (string)

          

          The action payload. This name can be customized.

          

          

        

      dynamoDBv2 -> (structure)

        

        Write to a DynamoDB table. This is a new version of the DynamoDB action. It allows you to write each attribute in an MQTT message payload into a separate DynamoDB column.

        

        roleArn -> (string)

          

          The ARN of the IAM role that grants access to the DynamoDB table.

          

          

        putItem -> (structure)

          

          Specifies the DynamoDB table to which the message data will be written. For example:

           

           ``{ "dynamoDBv2": { "roleArn": "aws:iam:12341251:my-role" "putItem": { "tableName": "my-table" } } }``  

           

          Each attribute in the message payload will be written to a separate column in the DynamoDB database.

          

          tableName -> (string)

            

            The table where the message data will be written

            

            

          

        

      lambda -> (structure)

        

        Invoke a Lambda function.

        

        functionArn -> (string)

          

          The ARN of the Lambda function.

          

          

        

      sns -> (structure)

        

        Publish to an Amazon SNS topic.

        

        targetArn -> (string)

          

          The ARN of the SNS topic.

          

          

        roleArn -> (string)

          

          The ARN of the IAM role that grants access.

          

          

        messageFormat -> (string)

          

          The message format of the message to publish. Optional. Accepted values are "JSON" and "RAW". The default value of the attribute is "RAW". SNS uses this setting to determine if the payload should be parsed and relevant platform-specific bits of the payload should be extracted. To read more about SNS message formats, see `http\://docs.aws.amazon.com/sns/latest/dg/json-formats.html <http://docs.aws.amazon.com/sns/latest/dg/json-formats.html>`_ refer to their official documentation.

          

          

        

      sqs -> (structure)

        

        Publish to an Amazon SQS queue.

        

        roleArn -> (string)

          

          The ARN of the IAM role that grants access.

          

          

        queueUrl -> (string)

          

          The URL of the Amazon SQS queue.

          

          

        useBase64 -> (boolean)

          

          Specifies whether to use Base64 encoding.

          

          

        

      kinesis -> (structure)

        

        Write data to an Amazon Kinesis stream.

        

        roleArn -> (string)

          

          The ARN of the IAM role that grants access to the Amazon Kinesis stream.

          

          

        streamName -> (string)

          

          The name of the Amazon Kinesis stream.

          

          

        partitionKey -> (string)

          

          The partition key.

          

          

        

      republish -> (structure)

        

        Publish to another MQTT topic.

        

        roleArn -> (string)

          

          The ARN of the IAM role that grants access.

          

          

        topic -> (string)

          

          The name of the MQTT topic.

          

          

        

      s3 -> (structure)

        

        Write to an Amazon S3 bucket.

        

        roleArn -> (string)

          

          The ARN of the IAM role that grants access.

          

          

        bucketName -> (string)

          

          The Amazon S3 bucket.

          

          

        key -> (string)

          

          The object key.

          

          

        cannedAcl -> (string)

          

          The Amazon S3 canned ACL that controls access to the object identified by the object key. For more information, see `S3 canned ACLs <http://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl>`_ .

          

          

        

      firehose -> (structure)

        

        Write to an Amazon Kinesis Firehose stream.

        

        roleArn -> (string)

          

          The IAM role that grants access to the Amazon Kinesis Firehost stream.

          

          

        deliveryStreamName -> (string)

          

          The delivery stream name.

          

          

        separator -> (string)

          

          A character separator that will be used to separate records written to the Firehose stream. Valid values are: '\n' (newline), '\t' (tab), '\r\n' (Windows newline), ',' (comma).

          

          

        

      cloudwatchMetric -> (structure)

        

        Capture a CloudWatch metric.

        

        roleArn -> (string)

          

          The IAM role that allows access to the CloudWatch metric.

          

          

        metricNamespace -> (string)

          

          The CloudWatch metric namespace name.

          

          

        metricName -> (string)

          

          The CloudWatch metric name.

          

          

        metricValue -> (string)

          

          The CloudWatch metric value.

          

          

        metricUnit -> (string)

          

          The `metric unit <http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#Unit>`_ supported by CloudWatch.

          

          

        metricTimestamp -> (string)

          

          An optional `Unix timestamp <http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#about_timestamp>`_ .

          

          

        

      cloudwatchAlarm -> (structure)

        

        Change the state of a CloudWatch alarm.

        

        roleArn -> (string)

          

          The IAM role that allows access to the CloudWatch alarm.

          

          

        alarmName -> (string)

          

          The CloudWatch alarm name.

          

          

        stateReason -> (string)

          

          The reason for the alarm change.

          

          

        stateValue -> (string)

          

          The value of the alarm state. Acceptable values are: OK, ALARM, INSUFFICIENT_DATA.

          

          

        

      elasticsearch -> (structure)

        

        Write data to an Amazon Elasticsearch Service domain.

        

        roleArn -> (string)

          

          The IAM role ARN that has access to Elasticsearch.

          

          

        endpoint -> (string)

          

          The endpoint of your Elasticsearch domain.

          

          

        index -> (string)

          

          The Elasticsearch index where you want to store your data.

          

          

        type -> (string)

          

          The type of document you are storing.

          

          

        id -> (string)

          

          The unique identifier for the document you are storing.

          

          

        

      salesforce -> (structure)

        

        Send a message to a Salesforce IoT Cloud Input Stream.

        

        token -> (string)

          

          The token used to authenticate access to the Salesforce IoT Cloud Input Stream. The token is available from the Salesforce IoT Cloud platform after creation of the Input Stream.

          

          

        url -> (string)

          

          The URL exposed by the Salesforce IoT Cloud Input Stream. The URL is available from the Salesforce IoT Cloud platform after creation of the Input Stream.

          

          

        

      

    

  ruleDisabled -> (boolean)

    

    Specifies whether the rule is disabled.

    

    

  awsIotSqlVersion -> (string)

    

    The version of the SQL rules engine to use when evaluating the rule.

    

    

  

