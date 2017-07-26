[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events put-targets:


***********
put-targets
***********



===========
Description
===========



Adds the specified targets to the specified rule, or updates the targets if they are already associated with the rule.

 

Targets are the resources that are invoked when a rule is triggered.

 

You can configure the following as targets for CloudWatch Events:

 

 
* EC2 instances 
 
* AWS Lambda functions 
 
* Streams in Amazon Kinesis Streams 
 
* Delivery streams in Amazon Kinesis Firehose 
 
* Amazon ECS tasks 
 
* AWS Step Functions state machines 
 
* Amazon SNS topics 
 
* Amazon SQS queues 
 

 

Note that creating rules with built-in targets is supported only in the AWS Management Console.

 

For some target types, ``put-targets`` provides target-specific parameters. If the target is an Amazon Kinesis stream, you can optionally specify which shard the event goes to by using the ``KinesisParameters`` argument. To invoke a command on multiple EC2 instances with one rule, you can use the ``RunCommandParameters`` field.

 

To be able to make API calls against the resources that you own, Amazon CloudWatch Events needs the appropriate permissions. For AWS Lambda and Amazon SNS resources, CloudWatch Events relies on resource-based policies. For EC2 instances, Amazon Kinesis streams, and AWS Step Functions state machines, CloudWatch Events relies on IAM roles that you specify in the ``RoleARN`` argument in ``put-targets`` . For more information, see `Authentication and Access Control <http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/auth-and-access-control-cwe.html>`_ in the *Amazon CloudWatch Events User Guide* .

 

If another AWS account is in the same region and has granted you permission (using ``put-permission`` ), you can set that account's event bus as a target of the rules in your account. To send the matched events to the other account, specify that account's event bus as the ``Arn`` when you run ``put-targets`` . For more information about enabling cross-account events, see  put-permission .

 

 **Input** , **InputPath** and **InputTransformer** are mutually exclusive and optional parameters of a target. When a rule is triggered due to a matched event:

 

 
* If none of the following arguments are specified for a target, then the entire event is passed to the target in JSON form (unless the target is Amazon EC2 Run Command or Amazon ECS task, in which case nothing from the event is passed to the target). 
 
* If **Input** is specified in the form of valid JSON, then the matched event is overridden with this constant. 
 
* If **InputPath** is specified in the form of JSONPath (for example, ``$.detail`` ), then only the part of the event specified in the path is passed to the target (for example, only the detail part of the event is passed). 
 
* If **InputTransformer** is specified, then one or more specified JSONPaths are extracted from the event and used as values in a template that you specify as the input to the target. 
 

 

When you specify ``Input`` , ``InputPath`` , or ``InputTransformer`` , you must use JSON dot notation, not bracket notation.

 

When you add targets to a rule and the associated rule triggers soon after, new or updated targets might not be immediately invoked. Please allow a short period of time for changes to take effect.

 

This action can partially fail if too many requests are made at the same time. If that happens, ``FailedEntryCount`` is non-zero in the response and each entry in ``FailedEntries`` provides the ID of the failed target and the error code.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/PutTargets>`_


========
Synopsis
========

::

    put-targets
  --rule <value>
  --targets <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule`` (string)


  The name of the rule.

  

``--targets`` (list)


  The targets to update or add to the rule.

  



JSON Syntax::

  [
    {
      "Id": "string",
      "Arn": "string",
      "RoleArn": "string",
      "Input": "string",
      "InputPath": "string",
      "InputTransformer": {
        "InputPathsMap": {"string": "string"
          ...},
        "InputTemplate": "string"
      },
      "KinesisParameters": {
        "PartitionKeyPath": "string"
      },
      "RunCommandParameters": {
        "RunCommandTargets": [
          {
            "Key": "string",
            "Values": ["string", ...]
          }
          ...
        ]
      },
      "EcsParameters": {
        "TaskDefinitionArn": "string",
        "TaskCount": integer
      }
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To add targets for CloudWatch Events rules**

This example adds a Lambda function as the target of a rule::

  aws events put-targets --rule DailyLambdaFunction --targets "Id"="1","Arn"="arn:aws:lambda:us-east-1:123456789012:function:MyFunctionName" 

This example sets an Amazon Kinesis stream as the target, so that events caught by this rule are relayed to the stream::

  aws events put-targets --rule EC2InstanceStateChanges --targets "Id"="1","Arn"="arn:aws:kinesis:us-east-1:123456789012:stream/MyStream","RoleArn"="arn:aws:iam::123456789012:role/MyRoleForThisRule"

This example sets two Amazon Kinesis streams as targets for one rule::

  aws events put-targets --rule DailyLambdaFunction --targets "Id"="Target1","Arn"="arn:aws:kinesis:us-east-1:379642911888:stream/MyStream1","RoleArn"="arn:aws:iam::379642911888:role/ MyRoleToAccessLambda"  "Id"="Target2"," Arn"="arn:aws:kinesis:us-east-1:379642911888:stream/MyStream2","RoleArn"="arn:aws:iam::379642911888:role/MyRoleToAccessLambda


======
Output
======

FailedEntryCount -> (integer)

  

  The number of failed entries.

  

  

FailedEntries -> (list)

  

  The failed target entries.

  

  (structure)

    

    Represents a target that failed to be added to a rule.

    

    TargetId -> (string)

      

      The ID of the target.

      

      

    ErrorCode -> (string)

      

      The error code that indicates why the target addition failed. If the value is ``ConcurrentModificationException`` , too many requests were made at the same time.

      

      

    ErrorMessage -> (string)

      

      The error message that explains why the target addition failed.

      

      

    

  

