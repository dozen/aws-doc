[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice put-evaluations:


***************
put-evaluations
***************



===========
Description
===========



Used by an AWS Lambda function to deliver evaluation results to AWS Config. This action is required in every AWS Lambda function that is invoked by an AWS Config rule.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/PutEvaluations>`_


========
Synopsis
========

::

    put-evaluations
  [--evaluations <value>]
  --result-token <value>
  [--test-mode | --no-test-mode]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--evaluations`` (list)


  The assessments that the AWS Lambda function performs. Each evaluation identifies an AWS resource and indicates whether it complies with the AWS Config rule that invokes the AWS Lambda function.

  



Shorthand Syntax::

    ComplianceResourceType=string,ComplianceResourceId=string,ComplianceType=string,Annotation=string,OrderingTimestamp=timestamp ...




JSON Syntax::

  [
    {
      "ComplianceResourceType": "string",
      "ComplianceResourceId": "string",
      "ComplianceType": "COMPLIANT"|"NON_COMPLIANT"|"NOT_APPLICABLE"|"INSUFFICIENT_DATA",
      "Annotation": "string",
      "OrderingTimestamp": timestamp
    }
    ...
  ]



``--result-token`` (string)


  An encrypted token that associates an evaluation with an AWS Config rule. Identifies the rule and the event that triggered the evaluation

  

``--test-mode`` | ``--no-test-mode`` (boolean)


  Use this parameter to specify a test run for ``put-evaluations`` . You can verify whether your AWS Lambda function will deliver evaluation results to AWS Config. No updates occur to your existing evaluations, and evaluation results are not sent to AWS Config.

   

  .. note::

     

    When ``TestMode`` is ``true`` , ``put-evaluations`` doesn't require a valid value for the ``ResultToken`` parameter, but the value cannot be null.

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FailedEvaluations -> (list)

  

  Requests that failed because of a client or server error.

  

  (structure)

    

    Identifies an AWS resource and indicates whether it complies with the AWS Config rule that it was evaluated against.

    

    ComplianceResourceType -> (string)

      

      The type of AWS resource that was evaluated.

      

      

    ComplianceResourceId -> (string)

      

      The ID of the AWS resource that was evaluated.

      

      

    ComplianceType -> (string)

      

      Indicates whether the AWS resource complies with the AWS Config rule that it was evaluated against.

       

      For the ``Evaluation`` data type, AWS Config supports only the ``COMPLIANT`` , ``NON_COMPLIANT`` , and ``NOT_APPLICABLE`` values. AWS Config does not support the ``INSUFFICIENT_DATA`` value for this data type.

       

      Similarly, AWS Config does not accept ``INSUFFICIENT_DATA`` as the value for ``ComplianceType`` from a ``put-evaluations`` request. For example, an AWS Lambda function for a custom Config rule cannot pass an ``INSUFFICIENT_DATA`` value to AWS Config.

      

      

    Annotation -> (string)

      

      Supplementary information about how the evaluation determined the compliance.

      

      

    OrderingTimestamp -> (timestamp)

      

      The time of the event in AWS Config that triggered the evaluation. For event-based evaluations, the time indicates when AWS Config created the configuration item that triggered the evaluation. For periodic evaluations, the time indicates when AWS Config triggered the evaluation at the frequency that you specified (for example, every 24 hours).

      

      

    

  

