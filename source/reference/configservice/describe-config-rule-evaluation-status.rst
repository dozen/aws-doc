[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice describe-config-rule-evaluation-status:


**************************************
describe-config-rule-evaluation-status
**************************************



===========
Description
===========



Returns status information for each of your AWS managed Config rules. The status includes information such as the last time AWS Config invoked the rule, the last time AWS Config failed to invoke the rule, and the related error for the last failure.



========
Synopsis
========

::

    describe-config-rule-evaluation-status
  [--config-rule-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--config-rule-names`` (list)


  The name of the AWS managed Config rules for which you want status information. If you do not specify any names, AWS Config returns status information for all AWS managed Config rules that you use. 

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get status information for an AWS Config rule**

The following command returns the status information for an AWS Config rule named ``MyConfigRule``::

    aws configservice describe-config-rule-evaluation-status --config-rule-names MyConfigRule

Output::

    {
        "ConfigRulesEvaluationStatus": [
            {
                "ConfigRuleArn": "arn:aws:config:us-east-1:123456789012:config-rule/config-rule-abcdef",
                "FirstActivatedTime": 1450311703.844,
                "ConfigRuleId": "config-rule-abcdef",
                "LastSuccessfulInvocationTime": 1450314643.156,
                "ConfigRuleName": "MyConfigRule"
            }
        ]
    }

======
Output
======

ConfigRulesEvaluationStatus -> (list)

  

  Status information about your AWS managed Config rules.

  

  (structure)

    

    Status information for your AWS managed Config rules. The status includes information such as the last time the rule ran, the last time it failed, and the related error for the last failure.

     

    This action does not return status information about customer managed Config rules.

    

    ConfigRuleName -> (string)

      

      The name of the AWS Config rule.

      

      

    ConfigRuleArn -> (string)

      

      The Amazon Resource Name (ARN) of the AWS Config rule.

      

      

    ConfigRuleId -> (string)

      

      The ID of the AWS Config rule.

      

      

    LastSuccessfulInvocationTime -> (timestamp)

      

      The time that AWS Config last successfully invoked the AWS Config rule to evaluate your AWS resources.

      

      

    LastFailedInvocationTime -> (timestamp)

      

      The time that AWS Config last failed to invoke the AWS Config rule to evaluate your AWS resources.

      

      

    LastSuccessfulEvaluationTime -> (timestamp)

      

      The time that AWS Config last successfully evaluated your AWS resources against the rule.

      

      

    LastFailedEvaluationTime -> (timestamp)

      

      The time that AWS Config last failed to evaluate your AWS resources against the rule.

      

      

    FirstActivatedTime -> (timestamp)

      

      The time that you first activated the AWS Config rule.

      

      

    LastErrorCode -> (string)

      

      The error code that AWS Config returned when the rule last failed.

      

      

    LastErrorMessage -> (string)

      

      The error message that AWS Config returned when the rule last failed.

      

      

    FirstEvaluationStarted -> (boolean)

      

      Indicates whether AWS Config has evaluated your resources against the rule at least once.

       

       
      * ``true`` - AWS Config has evaluated your AWS resources against the rule at least once.
       
      * ``false`` - AWS Config has not once finished evaluating your AWS resources against the rule.
       

      

      

    

  

