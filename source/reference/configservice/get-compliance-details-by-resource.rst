[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice get-compliance-details-by-resource:


**********************************
get-compliance-details-by-resource
**********************************



===========
Description
===========



Returns the evaluation results for the specified AWS resource. The results indicate which AWS Config rules were used to evaluate the resource, when each rule was last used, and whether the resource complies with each rule.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/GetComplianceDetailsByResource>`_


``get-compliance-details-by-resource`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``EvaluationResults``


========
Synopsis
========

::

    get-compliance-details-by-resource
  --resource-type <value>
  --resource-id <value>
  [--compliance-types <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-type`` (string)


  The type of the AWS resource for which you want compliance information.

  

``--resource-id`` (string)


  The ID of the AWS resource for which you want compliance information.

  

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

**To get the evaluation results for an AWS resource**

The following command returns the evaluation results for each rule with which the EC2 instance ``i-1a2b3c4d`` does not comply::

    aws configservice get-compliance-details-by-resource --resource-type AWS::EC2::Instance --resource-id i-1a2b3c4d --compliance-types NON_COMPLIANT

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
                "ResultRecordedTime": 1450314643.288,
                "ConfigRuleInvokedTime": 1450314643.034,
                "ComplianceType": "NON_COMPLIANT"
            },
            {
                "EvaluationResultIdentifier": {
                    "OrderingTimestamp": 1450314635.065,
                    "EvaluationResultQualifier": {
                        "ResourceType": "AWS::EC2::Instance",
                        "ResourceId": "i-1a2b3c4d",
                        "ConfigRuleName": "RequiredTagForEC2Instances"
                    }
                },
                "ResultRecordedTime": 1450314645.261,
                "ConfigRuleInvokedTime": 1450314642.948,
                "ComplianceType": "NON_COMPLIANT"
            }
        ]
    }

======
Output
======

EvaluationResults -> (list)

  

  Indicates whether the specified AWS resource complies each AWS Config rule.

  

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

  

  

