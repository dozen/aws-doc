[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice describe-config-rules:


*********************
describe-config-rules
*********************



===========
Description
===========



Returns details about your AWS Config rules.



========
Synopsis
========

::

    describe-config-rules
  [--config-rule-names <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--config-rule-names`` (list)


  The names of the AWS Config rules for which you want details. If you do not specify any names, AWS Config returns details for all your rules.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The ``nextToken`` string returned on a previous page that you use to get the next page of results in a paginated response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get details for an AWS Config rule**

The following command returns details for an AWS Config rule named ``InstanceTypesAreT2micro``::

    aws configservice describe-config-rules --config-rule-names InstanceTypesAreT2micro

Output::

    {
        "ConfigRules": [
            {
                "ConfigRuleState": "ACTIVE",
                "Description": "Evaluates whether EC2 instances are the t2.micro type.",
                "ConfigRuleName": "InstanceTypesAreT2micro",
                "ConfigRuleArn": "arn:aws:config:us-east-1:123456789012:config-rule/config-rule-abcdef",
                "Source": {
                    "Owner": "CUSTOM_LAMBDA",
                    "SourceIdentifier": "arn:aws:lambda:us-east-1:123456789012:function:InstanceTypeCheck",
                    "SourceDetails": [
                        {
                            "EventSource": "aws.config",
                            "MessageType": "ConfigurationItemChangeNotification"
                        }
                    ]
                },
                "InputParameters": "{\"desiredInstanceType\":\"t2.micro\"}",
                "Scope": {
                    "ComplianceResourceTypes": [
                        "AWS::EC2::Instance"
                    ]
                },
                "ConfigRuleId": "config-rule-abcdef"
            }
        ]
    }

======
Output
======

ConfigRules -> (list)

  

  The details about your AWS Config rules.

  

  (structure)

    

    An AWS Lambda function that evaluates configuration items to assess whether your AWS resources comply with your desired configurations. This function can run when AWS Config detects a configuration change or delivers a configuration snapshot.

     

    For more information about developing and using AWS Config rules, see `Evaluating AWS Resource Configurations with AWS Config`_ in the *AWS Config Developer Guide* .

    

    ConfigRuleName -> (string)

      

      The name that you assign to the AWS Config rule. The name is required if you are adding a new rule.

      

      

    ConfigRuleArn -> (string)

      

      The Amazon Resource Name (ARN) of the AWS Config rule.

      

      

    ConfigRuleId -> (string)

      

      The ID of the AWS Config rule.

      

      

    Description -> (string)

      

      The description that you provide for the AWS Config rule.

      

      

    Scope -> (structure)

      

      Defines which resources can trigger an evaluation for the rule. The scope can include one or more resource types, a combination of one resource type and one resource ID, or a combination of a tag key and value. Specify a scope to constrain the resources that can trigger an evaluation for the rule. If you do not specify a scope, evaluations are triggered when any resource in the recording group changes.

      

      ComplianceResourceTypes -> (list)

        

        The resource types of only those AWS resources that you want to trigger an evaluation for the rule. You can only specify one type if you also specify a resource ID for ``ComplianceResourceId`` .

        

        (string)

          

          

        

      TagKey -> (string)

        

        The tag key that is applied to only those AWS resources that you want you want to trigger an evaluation for the rule.

        

        

      TagValue -> (string)

        

        The tag value applied to only those AWS resources that you want to trigger an evaluation for the rule. If you specify a value for ``TagValue`` , you must also specify a value for ``TagKey`` .

        

        

      ComplianceResourceId -> (string)

        

        The IDs of the only AWS resource that you want to trigger an evaluation for the rule. If you specify a resource ID, you must specify one resource type for ``ComplianceResourceTypes`` .

        

        

      

    Source -> (structure)

      

      Provides the rule owner (AWS or customer), the rule identifier, and the events that cause the function to evaluate your AWS resources.

      

      Owner -> (string)

        

        Indicates whether AWS or the customer owns and manages the AWS Config rule.

        

        

      SourceIdentifier -> (string)

        

        For AWS managed Config rules, a pre-defined identifier from a list. To reference the list, see `Using AWS Managed Config Rules`_ .

         

        For customer managed Config rules, the identifier is the Amazon Resource Name (ARN) of the rule's AWS Lambda function.

        

        

      SourceDetails -> (list)

        

        Provides the source and type of the event that causes AWS Config to evaluate your AWS resources.

        

        (structure)

          

          Provides the source and type of the event that triggers AWS Config to evaluate your AWS resources against a rule.

          

          EventSource -> (string)

            

            The source of the event, such as an AWS service, that triggers AWS Config to evaluate your AWS resources.

            

            

          MessageType -> (string)

            

            The type of SNS message that triggers AWS Config to run an evaluation. For evaluations that are initiated when AWS Config delivers a configuration item change notification, you must use ``ConfigurationItemChangeNotification`` . For evaluations that are initiated when AWS Config delivers a configuration snapshot, you must use ``ConfigurationSnapshotDeliveryCompleted`` . 

            

            

          

        

      

    InputParameters -> (string)

      

      A string in JSON format that is passed to the AWS Config rule Lambda function.

      

      

    MaximumExecutionFrequency -> (string)

      

      The maximum frequency at which the AWS Config rule runs evaluations.

       

      If your rule is periodic, meaning it runs an evaluation when AWS Config delivers a configuration snapshot, then it cannot run evaluations more frequently than AWS Config delivers the snapshots. For periodic rules, set the value of the ``MaximumExecutionFrequency`` key to be equal to or greater than the value of the ``deliveryFrequency`` key, which is part of ``ConfigSnapshotDeliveryProperties`` . To update the frequency with which AWS Config delivers your snapshots, use the ``put-delivery-channel`` action.

      

      

    ConfigRuleState -> (string)

      

      Indicates whether the AWS Config rule is active or currently being deleted by AWS Config.

       

      AWS Config sets the state of a rule to ``DELETING`` temporarily after you use the ``delete-config-rule`` request to delete the rule. After AWS Config finishes deleting a rule, the rule and all of its evaluations are erased and no longer available.

       

      You cannot add a rule to AWS Config that has the state set to ``DELETING`` . If you want to delete a rule, you must use the ``delete-config-rule`` request.

      

      

    

  

NextToken -> (string)

  

  The string that you use in a subsequent request to get the next page of results in a paginated response.

  

  



.. _Using AWS Managed Config Rules: http://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_use-managed-rules.html
.. _Evaluating AWS Resource Configurations with AWS Config: http://docs.aws.amazon.com/config/latest/developerguide/evaluate-config.html
