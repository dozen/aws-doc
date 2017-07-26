[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice describe-config-rules:


*********************
describe-config-rules
*********************



===========
Description
===========



Returns details about your AWS Config rules.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/DescribeConfigRules>`_


``describe-config-rules`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ConfigRules``


========
Synopsis
========

::

    describe-config-rules
  [--config-rule-names <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--config-rule-names`` (list)


  The names of the AWS Config rules for which you want details. If you do not specify any names, AWS Config returns details for all your rules.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    An AWS Config rule represents an AWS Lambda function that you create for a custom rule or a predefined function for an AWS managed rule. The function evaluates configuration items to assess whether your AWS resources comply with your desired configurations. This function can run when AWS Config detects a configuration change to an AWS resource and at a periodic frequency that you choose (for example, every 24 hours).

     

    .. note::

       

      You can use the AWS CLI and AWS SDKs if you want to create a rule that triggers evaluations for your resources when AWS Config delivers the configuration snapshot. For more information, see  ConfigSnapshotDeliveryProperties .

       

     

    For more information about developing and using AWS Config rules, see `Evaluating AWS Resource Configurations with AWS Config <http://docs.aws.amazon.com/config/latest/developerguide/evaluate-config.html>`_ in the *AWS Config Developer Guide* .

    

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

      

      Provides the rule owner (AWS or customer), the rule identifier, and the notifications that cause the function to evaluate your AWS resources.

      

      Owner -> (string)

        

        Indicates whether AWS or the customer owns and manages the AWS Config rule.

        

        

      SourceIdentifier -> (string)

        

        For AWS Config managed rules, a predefined identifier from a list. For example, ``IAM_PASSWORD_POLICY`` is a managed rule. To reference a managed rule, see `Using AWS Managed Config Rules <http://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_use-managed-rules.html>`_ .

         

        For custom rules, the identifier is the Amazon Resource Name (ARN) of the rule's AWS Lambda function, such as ``arn:aws:lambda:us-east-1:123456789012:function:custom_rule_name`` .

        

        

      SourceDetails -> (list)

        

        Provides the source and type of the event that causes AWS Config to evaluate your AWS resources.

        

        (structure)

          

          Provides the source and the message types that trigger AWS Config to evaluate your AWS resources against a rule. It also provides the frequency with which you want AWS Config to run evaluations for the rule if the trigger type is periodic. You can specify the parameter values for ``SourceDetail`` only for custom rules. 

          

          EventSource -> (string)

            

            The source of the event, such as an AWS service, that triggers AWS Config to evaluate your AWS resources.

            

            

          MessageType -> (string)

            

            The type of notification that triggers AWS Config to run an evaluation for a rule. You can specify the following notification types:

             

             
            * ``ConfigurationItemChangeNotification`` - Triggers an evaluation when AWS Config delivers a configuration item as a result of a resource change. 
             
            * ``OversizedConfigurationItemChangeNotification`` - Triggers an evaluation when AWS Config delivers an oversized configuration item. AWS Config may generate this notification type when a resource changes and the notification exceeds the maximum size allowed by Amazon SNS. 
             
            * ``ScheduledNotification`` - Triggers a periodic evaluation at the frequency specified for ``MaximumExecutionFrequency`` . 
             
            * ``ConfigurationSnapshotDeliveryCompleted`` - Triggers a periodic evaluation when AWS Config delivers a configuration snapshot. 
             

             

            If you want your custom rule to be triggered by configuration changes, specify both ``ConfigurationItemChangeNotification`` and ``OversizedConfigurationItemChangeNotification`` . 

            

            

          MaximumExecutionFrequency -> (string)

            

            The frequency that you want AWS Config to run evaluations for a custom rule with a periodic trigger. If you specify a value for ``MaximumExecutionFrequency`` , then ``MessageType`` must use the ``ScheduledNotification`` value.

             

            .. note::

               

              By default, rules with a periodic trigger are evaluated every 24 hours. To change the frequency, specify a valid value for the ``MaximumExecutionFrequency`` parameter.

               

            

            

          

        

      

    InputParameters -> (string)

      

      A string in JSON format that is passed to the AWS Config rule Lambda function.

      

      

    MaximumExecutionFrequency -> (string)

      

      The maximum frequency with which AWS Config runs evaluations for a rule. You can specify a value for ``MaximumExecutionFrequency`` when:

       

       
      * You are using an AWS managed rule that is triggered at a periodic frequency. 
       
      * Your custom rule is triggered when AWS Config delivers the configuration snapshot. For more information, see  ConfigSnapshotDeliveryProperties . 
       

       

      .. note::

         

        By default, rules with a periodic trigger are evaluated every 24 hours. To change the frequency, specify a valid value for the ``MaximumExecutionFrequency`` parameter.

         

      

      

    ConfigRuleState -> (string)

      

      Indicates whether the AWS Config rule is active or is currently being deleted by AWS Config. It can also indicate the evaluation status for the Config rule.

       

      AWS Config sets the state of the rule to ``EVALUATING`` temporarily after you use the ``start-config-rules-evaluation`` request to evaluate your resources against the Config rule.

       

      AWS Config sets the state of the rule to ``DELETING_RESULTS`` temporarily after you use the ``delete-evaluation-results`` request to delete the current evaluation results for the Config rule.

       

      AWS Config sets the state of a rule to ``DELETING`` temporarily after you use the ``delete-config-rule`` request to delete the rule. After AWS Config deletes the rule, the rule and all of its evaluations are erased and are no longer available.

      

      

    

  

NextToken -> (string)

  

  The string that you use in a subsequent request to get the next page of results in a paginated response.

  

  

