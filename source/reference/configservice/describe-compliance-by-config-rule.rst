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
 
* The rule's AWS Lambda function is failing to send evaluation results to AWS Config. Verify that the role that you assigned to your configuration recorder includes the ``config:PutEvaluations`` permission. If the rule is a customer managed rule, verify that the AWS Lambda execution role includes the ``config:PutEvaluations`` permission.
 
* The rule's AWS Lambda function has returned ``NOT_APPLICABLE`` for all evaluation results. This can occur if the resources were deleted or removed from the rule's scope.






========
Synopsis
========

::

    describe-compliance-by-config-rule
  [--config-rule-names <value>]
  [--compliance-types <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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





``--next-token`` (string)


  The ``nextToken`` string returned on a previous page that you use to get the next page of results in a paginated response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

        

        The number of AWS resources or AWS Config rules that cause a result of ``NON_COMPLIANT`` , up to a maximum of 25.

        

        CappedCount -> (integer)

          

          The number of AWS resources or AWS Config rules responsible for the current compliance of the item.

          

          

        CapExceeded -> (boolean)

          

          Indicates whether the maximum count is reached.

          

          

        

      

    

  

NextToken -> (string)

  

  The string that you use in a subsequent request to get the next page of results in a paginated response.

  

  

