[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice get-compliance-summary-by-resource-type:


***************************************
get-compliance-summary-by-resource-type
***************************************



===========
Description
===========



Returns the number of resources that are compliant and the number that are noncompliant. You can specify one or more resource types to get these numbers for each resource type. The maximum number returned is 100.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/GetComplianceSummaryByResourceType>`_


========
Synopsis
========

::

    get-compliance-summary-by-resource-type
  [--resource-types <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-types`` (list)


  Specify one or more resource types to get the number of resources that are compliant and the number that are noncompliant for each resource type.

   

  For this request, you can specify an AWS resource type such as ``AWS::EC2::Instance`` , and you can specify that the resource type is an AWS account by specifying ``AWS::::Account`` .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the compliance summary for all resource types**

The following command returns the number of AWS resources that are noncompliant and the number that are compliant::

    aws configservice get-compliance-summary-by-resource-type

In the output, the value for each ``CappedCount`` attribute indicates how many resources are compliant or noncompliant.

Output::

    {
        "ComplianceSummariesByResourceType": [
            {
                "ComplianceSummary": {
                    "NonCompliantResourceCount": {
                        "CappedCount": 16,
                        "CapExceeded": false
                    },
                    "ComplianceSummaryTimestamp": 1453237464.543,
                    "CompliantResourceCount": {
                        "CappedCount": 10,
                        "CapExceeded": false
                    }
                }
            }
        ]
    }

**To get the compliance summary for a specific resource type**

The following command returns the number of EC2 instances that are noncompliant and the number that are compliant::

    aws configservice get-compliance-summary-by-resource-type --resource-types AWS::EC2::Instance

In the output, the value for each ``CappedCount`` attribute indicates how many resources are compliant or noncompliant.

Output::

    {
        "ComplianceSummariesByResourceType": [
            {
                "ResourceType": "AWS::EC2::Instance",
                "ComplianceSummary": {
                    "NonCompliantResourceCount": {
                        "CappedCount": 3,
                        "CapExceeded": false
                    },
                    "ComplianceSummaryTimestamp": 1452204923.518,
                    "CompliantResourceCount": {
                        "CappedCount": 7,
                        "CapExceeded": false
                    }
                }
            }
        ]
    }

======
Output
======

ComplianceSummariesByResourceType -> (list)

  

  The number of resources that are compliant and the number that are noncompliant. If one or more resource types were provided with the request, the numbers are returned for each resource type. The maximum number returned is 100.

  

  (structure)

    

    The number of AWS resources of a specific type that are compliant or noncompliant, up to a maximum of 100 for each compliance.

    

    ResourceType -> (string)

      

      The type of AWS resource.

      

      

    ComplianceSummary -> (structure)

      

      The number of AWS resources that are compliant or noncompliant, up to a maximum of 100 for each compliance.

      

      CompliantResourceCount -> (structure)

        

        The number of AWS Config rules or AWS resources that are compliant, up to a maximum of 25 for rules and 100 for resources.

        

        CappedCount -> (integer)

          

          The number of AWS resources or AWS Config rules responsible for the current compliance of the item.

          

          

        CapExceeded -> (boolean)

          

          Indicates whether the maximum count is reached.

          

          

        

      NonCompliantResourceCount -> (structure)

        

        The number of AWS Config rules or AWS resources that are noncompliant, up to a maximum of 25 for rules and 100 for resources.

        

        CappedCount -> (integer)

          

          The number of AWS resources or AWS Config rules responsible for the current compliance of the item.

          

          

        CapExceeded -> (boolean)

          

          Indicates whether the maximum count is reached.

          

          

        

      ComplianceSummaryTimestamp -> (timestamp)

        

        The time that AWS Config created the compliance summary.

        

        

      

    

  

