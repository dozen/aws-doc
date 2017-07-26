[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice describe-compliance-by-resource:


*******************************
describe-compliance-by-resource
*******************************



===========
Description
===========



Indicates whether the specified AWS resources are compliant. If a resource is noncompliant, this action returns the number of AWS Config rules that the resource does not comply with. 

 

A resource is compliant if it complies with all the AWS Config rules that evaluate it. It is noncompliant if it does not comply with one or more of these rules.

 

If AWS Config has no current evaluation results for the resource, it returns ``INSUFFICIENT_DATA`` . This result might indicate one of the following conditions about the rules that evaluate the resource: 

 
* AWS Config has never invoked an evaluation for the rule. To check whether it has, use the ``describe-config-rule-evaluation-status`` action to get the ``LastSuccessfulInvocationTime`` and ``LastFailedInvocationTime`` .
 
* The rule's AWS Lambda function is failing to send evaluation results to AWS Config. Verify that the role that you assigned to your configuration recorder includes the ``config:PutEvaluations`` permission. If the rule is a customer managed rule, verify that the AWS Lambda execution role includes the ``config:PutEvaluations`` permission.
 
* The rule's AWS Lambda function has returned ``NOT_APPLICABLE`` for all evaluation results. This can occur if the resources were deleted or removed from the rule's scope.






========
Synopsis
========

::

    describe-compliance-by-resource
  [--resource-type <value>]
  [--resource-id <value>]
  [--compliance-types <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-type`` (string)


  The types of AWS resources for which you want compliance information; for example, ``AWS::EC2::Instance`` . For this action, you can specify that the resource type is an AWS account by specifying ``AWS::::Account`` .

  

``--resource-id`` (string)


  The ID of the AWS resource for which you want compliance information. You can specify only one resource ID. If you specify a resource ID, you must also specify a type for ``ResourceType`` .

  

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





``--limit`` (integer)


  The maximum number of evaluation results returned on each page. The default is 10. You cannot specify a limit greater than 100. If you specify 0, AWS Config uses the default.

  

``--next-token`` (string)


  The ``nextToken`` string returned on a previous page that you use to get the next page of results in a paginated response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get compliance information for your AWS resources**

The following command returns compliance information for each EC2 instance that is recorded by AWS Config and that violates one or more rules::

    aws configservice describe-compliance-by-resource --resource-type AWS::EC2::Instance --compliance-types NON_COMPLIANT

In the output, the value for each ``CappedCount`` attribute indicates how many rules the resource violates. For example, the following output indicates that instance ``i-1a2b3c4d`` violates 2 rules.

Output::

    {
        "ComplianceByResources": [
            {
                "ResourceType": "AWS::EC2::Instance",
                "ResourceId": "i-1a2b3c4d",
                "Compliance": {
                    "ComplianceContributorCount": {
                        "CappedCount": 2,
                        "CapExceeded": false
                    },
                    "ComplianceType": "NON_COMPLIANT"
                }
            },
            {
                "ResourceType": "AWS::EC2::Instance",
                "ResourceId": "i-2a2b3c4d ",
                "Compliance": {
                    "ComplianceContributorCount": {
                        "CappedCount": 3,
                        "CapExceeded": false
                    },
                    "ComplianceType": "NON_COMPLIANT"
                }
            }
        ]
    }

======
Output
======

ComplianceByResources -> (list)

  

  Indicates whether the specified AWS resource complies with all of the AWS Config rules that evaluate it.

  

  (structure)

    

    Indicates whether an AWS resource that is evaluated according to one or more AWS Config rules is compliant. A resource is compliant if it complies with all of the rules that evaluate it, and it is noncompliant if it does not comply with one or more of these rules. 

    

    ResourceType -> (string)

      

      The type of the AWS resource that was evaluated.

      

      

    ResourceId -> (string)

      

      The ID of the AWS resource that was evaluated.

      

      

    Compliance -> (structure)

      

      Indicates whether the AWS resource complies with all of the AWS Config rules that evaluated it.

      

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

  

  

