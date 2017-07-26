[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice start-config-rules-evaluation:


*****************************
start-config-rules-evaluation
*****************************



===========
Description
===========



Runs an on-demand evaluation for the specified Config rules against the last known configuration state of the resources. Use ``start-config-rules-evaluation`` when you want to test a rule that you updated is working as expected. ``start-config-rules-evaluation`` does not re-record the latest configuration state for your resources; it re-runs an evaluation against the last known state of your resources. 

 

You can specify up to 25 Config rules per request. 

 

An existing ``start-config-rules-evaluation`` call must complete for the specified rules before you can call the API again. If you chose to have AWS Config stream to an Amazon SNS topic, you will receive a ``ConfigRuleEvaluationStarted`` notification when the evaluation starts.

 

.. note::

   

  You don't need to call the ``start-config-rules-evaluation`` API to run an evaluation for a new rule. When you create a new rule, AWS Config automatically evaluates your resources against the rule. 

   

 

The ``start-config-rules-evaluation`` API is useful if you want to run on-demand evaluations, such as the following example:

 

 
* You have a custom rule that evaluates your IAM resources every 24 hours. 
 
* You update your Lambda function to add additional conditions to your rule. 
 
* Instead of waiting for the next periodic evaluation, you call the ``start-config-rules-evaluation`` API. 
 
* AWS Config invokes your Lambda function and evaluates your IAM resources. 
 
* Your custom rule will still run periodic evaluations every 24 hours. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/StartConfigRulesEvaluation>`_


========
Synopsis
========

::

    start-config-rules-evaluation
  [--config-rule-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--config-rule-names`` (list)


  The list of names of Config rules that you want to run evaluations for.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To run an on-demand evaluation for AWS Config rules**

The following command starts an evaluation for two AWS managed rules::

    aws configservice start-config-rules-evaluation --config-rule-names s3-bucket-versioning-enabled cloudtrail-enabled

======
Output
======

