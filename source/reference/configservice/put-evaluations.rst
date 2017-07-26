[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice put-evaluations:


***************
put-evaluations
***************



===========
Description
===========



Used by an AWS Lambda function to deliver evaluation results to AWS Config. This action is required in every AWS Lambda function that is invoked by an AWS Config rule.



========
Synopsis
========

::

    put-evaluations
  [--evaluations <value>]
  --result-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      The time of the event in AWS Config that triggered the evaluation. For event-based evaluations, the time indicates when AWS Config created the configuration item that triggered the evaluation. For periodic evaluations, the time indicates when AWS Config delivered the configuration snapshot that triggered the evaluation.

      

      

    

  

