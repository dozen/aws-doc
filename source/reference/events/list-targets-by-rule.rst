[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events list-targets-by-rule:


********************
list-targets-by-rule
********************



===========
Description
===========



Lists the targets assigned to the specified rule.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/ListTargetsByRule>`_


========
Synopsis
========

::

    list-targets-by-rule
  --rule <value>
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule`` (string)


  The name of the rule.

  

``--next-token`` (string)


  The token returned by a previous call to retrieve the next set of results.

  

``--limit`` (integer)


  The maximum number of results to return.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To display all the targets for a CloudWatch Events rule**

This example displays all the targets of the rule named DailyLambdaFunction::

  aws events list-targets-by-rule --rule  "DailyLambdaFunction"


======
Output
======

Targets -> (list)

  

  The targets assigned to the rule.

  

  (structure)

    

    Targets are the resources to be invoked when a rule is triggered. Target types include EC2 instances, AWS Lambda functions, Amazon Kinesis streams, Amazon ECS tasks, AWS Step Functions state machines, Run Command, and built-in targets.

    

    Id -> (string)

      

      The ID of the target.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) of the target.

      

      

    RoleArn -> (string)

      

      The Amazon Resource Name (ARN) of the IAM role to be used for this target when the rule is triggered. If one rule triggers multiple targets, you can use a different IAM role for each target.

      

      

    Input -> (string)

      

      Valid JSON text passed to the target. In this case, nothing from the event itself is passed to the target. You must use JSON dot notation, not bracket notation. For more information, see `The JavaScript Object Notation (JSON) Data Interchange Format <http://www.rfc-editor.org/rfc/rfc7159.txt>`_ .

      

      

    InputPath -> (string)

      

      The value of the JSONPath that is used for extracting part of the matched event when passing it to the target. You must use JSON dot notation, not bracket notation. For more information about JSON paths, see `JSONPath <http://goessner.net/articles/JsonPath/>`_ .

      

      

    InputTransformer -> (structure)

      

      Settings to enable you to provide custom input to a target based on certain event data. You can extract one or more key-value pairs from the event and then use that data to send customized input to the target.

      

      InputPathsMap -> (map)

        

        Map of JSON paths to be extracted from the event. These are key-value pairs, where each value is a JSON path. You must use JSON dot notation, not bracket notation.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      InputTemplate -> (string)

        

        Input template where you can use the values of the keys from ``InputPathsMap`` to customize the data sent to the target.

        

        

      

    KinesisParameters -> (structure)

      

      The custom parameter you can use to control shard assignment, when the target is an Amazon Kinesis stream. If you do not include this parameter, the default is to use the ``eventId`` as the partition key.

      

      PartitionKeyPath -> (string)

        

        The JSON path to be extracted from the event and used as the partition key. For more information, see `Amazon Kinesis Streams Key Concepts <http://docs.aws.amazon.com/streams/latest/dev/key-concepts.html#partition-key>`_ in the *Amazon Kinesis Streams Developer Guide* .

        

        

      

    RunCommandParameters -> (structure)

      

      Parameters used when you are using the rule to invoke Amazon EC2 Run Command.

      

      RunCommandTargets -> (list)

        

        Currently, we support including only one RunCommandTarget block, which specifies either an array of InstanceIds or a tag.

        

        (structure)

          

          Information about the EC2 instances that are to be sent the command, specified as key-value pairs. Each ``RunCommandTarget`` block can include only one key, but this key may specify multiple values.

          

          Key -> (string)

            

            Can be either ``tag:``  *tag-key* or ``InstanceIds`` .

            

            

          Values -> (list)

            

            If ``Key`` is ``tag:``  *tag-key* , ``Values`` is a list of tag values. If ``Key`` is ``InstanceIds`` , ``Values`` is a list of Amazon EC2 instance IDs.

            

            (string)

              

              

            

          

        

      

    EcsParameters -> (structure)

      

      Contains the Amazon ECS task definition and task count to be used, if the event target is an Amazon ECS task. For more information about Amazon ECS tasks, see `Task Definitions <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_defintions.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

      

      TaskDefinitionArn -> (string)

        

        The ARN of the task definition to use if the event target is an Amazon ECS cluster. 

        

        

      TaskCount -> (integer)

        

        The number of tasks to create based on the ``TaskDefinition`` . The default is one.

        

        

      

    

  

NextToken -> (string)

  

  Indicates whether there are additional results to retrieve. If there are no more results, the value is null.

  

  

