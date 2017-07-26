[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice describe-compliance-by-config-rule:


**********************************
describe-compliance-by-config-rule
**********************************



===========
Description
===========



Indicates whether the specified AWS Config rules are compliant. If a rule is noncompliant, this action returns the number of AWS resources that do not comply with the rule.

 

A rule is compliant if all of the evaluated resources comply with it, and it is noncompliant if any of these resources do not comply.

 

If AWS Config has no current evaluation results for the rule, it returns ``INSUFFICIENT_DATA`` . This result might indicate one of the following conditions:

 

 
* AWS Config has never invoked an evaluation for the rule. To check whether it has, use the ``describe-config-rule-evaluation-status`` action to get the ``LastSuccessfulInvocationTime`` and ``LastFailedInvocationTime`` . 
 
* The rule's AWS Lambda function is failing to send evaluation results to AWS Config. Verify that the role that you assigned to your configuration recorder includes the ``config:PutEvaluations`` permission. If the rule is a custom rule, verify that the AWS Lambda execution role includes the ``config:PutEvaluations`` permission. 
 
* The rule's AWS Lambda function has returned ``NOT_APPLICABLE`` for all evaluation results. This can occur if the resources were deleted or removed from the rule's scope. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/DescribeComplianceByConfigRule>`_


``describe-compliance-by-config-rule`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ComplianceByConfigRules``


========
Synopsis
========

::

    describe-compliance-by-config-rule
  [--config-rule-names <value>]
  [--compliance-types <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--config-rule-names`` (list)


  Specify one or more AWS Config rule names to filter the results by rule.

  



Syntax::

  "string" "string" ...



``--compliance-types`` (list)


  Filters the results by compliance.

   

  The allowed values are ``COMPLIANT`` , ``NON_COMPLIANT`` , and ``INSUFFICIENT_DATA`` .

  



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

**To get compliance information for your AWS Config rules**

The following command returns compliance information for each AWS Config rule that is violated by one or more AWS resources::

    aws configservice describe-compliance-by-config-rule --compliance-types NON_COMPLIANT

In the output, the value for each ``CappedCount`` attribute indicates how many resources do not comply with the related rule. For example, the following output indicates that 3 resources do not comply with the rule named ``InstanceTypesAreT2micro``.

Output::

    {
        "ComplianceByConfigRules": [
            {
                "Compliance": {
                    "ComplianceContributorCount": {
                        "CappedCount": 3,
                        "CapExceeded": false
                    },
                    "ComplianceType": "NON_COMPLIANT"
                },
                "ConfigRuleName": "InstanceTypesAreT2micro"
            },
            {
                "Compliance": {
                    "ComplianceContributorCount": {
                        "CappedCount": 10,
                        "CapExceeded": false
                    },
                    "ComplianceType": "NON_COMPLIANT"
                },
                "ConfigRuleName": "RequiredTagsForVolumes"
            }
        ]
    }

======
Output
======

ComplianceByConfigRules -> (list)

  

  Indicates whether each of the specified AWS Config rules is compliant.

  

  (structure)

    

    Indicates whether an AWS Config rule is compliant. A rule is compliant if all of the resources that the rule evaluated comply with it, and it is noncompliant if any of these resources do not comply.

    

    ConfigRuleName -> (string)

      

      The name of the AWS Config rule.

      

      

    Compliance -> (structure)

      

      Indicates whether the AWS Config rule is compliant.

      

      ComplianceType -> (string)

        

        Indicates whether an AWS resource or AWS Config rule is compliant.

         

        A resource is compliant if it complies with all of the AWS Config rules that evaluate it, and it is noncompliant if it does not comply with one or more of these rules.

         

        A rule is compliant if all of the resources that the rule evaluates comply with it, and it is noncompliant if any of these resources do not comply.

         

        AWS Config returns the ``INSUFFICIENT_DATA`` value when no evaluation results are available for the AWS resource or Config rule.

         

        For the ``Compliance`` data type, AWS Config supports only ``COMPLIANT`` , ``NON_COMPLIANT`` , and ``INSUFFICIENT_DATA`` values. AWS Config does not support the ``NOT_APPLICABLE`` value for the ``Compliance`` data type.

        

        

      ComplianceContributorCount -> (structure)

        

        The number of AWS resources or AWS Config rules that cause a result of ``NON_COMPLIANT`` , up to a maximum number.

        

        CappedCount -> (integer)

          

          The number of AWS resources or AWS Config rules responsible for the current compliance of the item.

          

          

        CapExceeded -> (boolean)

          

          Indicates whether the maximum count is reached.

          

          

        

      

    

  

NextToken -> (string)

  

  The string that you use in a subsequent request to get the next page of results in a paginated response.

  

  

