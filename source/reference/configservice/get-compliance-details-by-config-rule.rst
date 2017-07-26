[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice get-compliance-details-by-config-rule:


*************************************
get-compliance-details-by-config-rule
*************************************



===========
Description
===========



Returns the evaluation results for the specified AWS Config rule. The results indicate which AWS resources were evaluated by the rule, when each resource was last evaluated, and whether each resource complies with the rule.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/GetComplianceDetailsByConfigRule>`_


``get-compliance-details-by-config-rule`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``EvaluationResults``


========
Synopsis
========

::

    get-compliance-details-by-config-rule
  --config-rule-name <value>
  [--compliance-types <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--config-rule-name`` (string)


  The name of the AWS Config rule for which you want compliance information.

  

``--compliance-types`` (list)


  Filters the results by compliance.

   

  The allowed values are ``COMPLIANT`` , ``NON_COMPLIANT`` , and ``NOT_APPLICABLE`` .

  



Syntax::

  "string" "string" ...

  Where valid values are:
    COMPLIANT
    NON_COMPLIANT
    NOT_APPLICABLE
    INSUFFICIENT_DATA





``--limit`` (integer)


  The maximum number of evaluation results returned on each page. The default is 10. You cannot specify a limit greater than 100. If you specify 0, AWS Config uses the default.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the evaluation results for an AWS Config rule**

The following command returns the evaluation results for all of the resources that don't comply with an AWS Config rule named ``InstanceTypesAreT2micro``::

    aws configservice get-compliance-details-by-config-rule --config-rule-name InstanceTypesAreT2micro --compliance-types NON_COMPLIANT

Output::

    {
        "EvaluationResults": [
            {
                "EvaluationResultIdentifier": {
                    "OrderingTimestamp": 1450314635.065,
                    "EvaluationResultQualifier": {
                        "ResourceType": "AWS::EC2::Instance",
                        "ResourceId": "i-1a2b3c4d",
                        "ConfigRuleName": "InstanceTypesAreT2micro"
                    }
                },
                "ResultRecordedTime": 1450314645.261,
                "ConfigRuleInvokedTime": 1450314642.948,
                "ComplianceType": "NON_COMPLIANT"
            },
            {
                "EvaluationResultIdentifier": {
                    "OrderingTimestamp": 1450314635.065,
                    "EvaluationResultQualifier": {
                        "ResourceType": "AWS::EC2::Instance",
                        "ResourceId": "i-2a2b3c4d",
                        "ConfigRuleName": "InstanceTypesAreT2micro"
                    }
                },
                "ResultRecordedTime": 1450314645.18,
                "ConfigRuleInvokedTime": 1450314642.902,
                "ComplianceType": "NON_COMPLIANT"
            },
            {
                "EvaluationResultIdentifier": {
                    "OrderingTimestamp": 1450314635.065,
                    "EvaluationResultQualifier": {
                        "ResourceType": "AWS::EC2::Instance",
                        "ResourceId": "i-3a2b3c4d",
                        "ConfigRuleName": "InstanceTypesAreT2micro"
                    }
                },
                "ResultRecordedTime": 1450314643.346,
                "ConfigRuleInvokedTime": 1450314643.124,
                "ComplianceType": "NON_COMPLIANT"
            }
        ]
    }

======
Output
======

EvaluationResults -> (list)

  

  Indicates whether the AWS resource complies with the specified AWS Config rule.

  

  (structure)

    

    The details of an AWS Config evaluation. Provides the AWS resource that was evaluated, the compliance of the resource, related timestamps, and supplementary information.

    

    EvaluationResultIdentifier -> (structure)

      

      Uniquely identifies the evaluation result.

      

      EvaluationResultQualifier -> (structure)

        

        Identifies an AWS Config rule used to evaluate an AWS resource, and provides the type and ID of the evaluated resource.

        

        ConfigRuleName -> (string)

          

          The name of the AWS Config rule that was used in the evaluation.

          

          

        ResourceType -> (string)

          

          The type of AWS resource that was evaluated.

          

          

        ResourceId -> (string)

          

          The ID of the evaluated AWS resource.

          

          

        

      OrderingTimestamp -> (timestamp)

        

        The time of the event that triggered the evaluation of your AWS resources. The time can indicate when AWS Config delivered a configuration item change notification, or it can indicate when AWS Config delivered the configuration snapshot, depending on which event triggered the evaluation.

        

        

      

    ComplianceType -> (string)

      

      Indicates whether the AWS resource complies with the AWS Config rule that evaluated it.

       

      For the ``EvaluationResult`` data type, AWS Config supports only the ``COMPLIANT`` , ``NON_COMPLIANT`` , and ``NOT_APPLICABLE`` values. AWS Config does not support the ``INSUFFICIENT_DATA`` value for the ``EvaluationResult`` data type.

      

      

    ResultRecordedTime -> (timestamp)

      

      The time when AWS Config recorded the evaluation result.

      

      

    ConfigRuleInvokedTime -> (timestamp)

      

      The time when the AWS Config rule evaluated the AWS resource.

      

      

    Annotation -> (string)

      

      Supplementary information about how the evaluation determined the compliance.

      

      

    ResultToken -> (string)

      

      An encrypted token that associates an evaluation with an AWS Config rule. The token identifies the rule, the AWS resource being evaluated, and the event that triggered the evaluation.

      

      

    

  

NextToken -> (string)

  

  The string that you use in a subsequent request to get the next page of results in a paginated response.

  

  

