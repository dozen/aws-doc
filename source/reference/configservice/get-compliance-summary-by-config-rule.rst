[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice get-compliance-summary-by-config-rule:


*************************************
get-compliance-summary-by-config-rule
*************************************



===========
Description
===========



Returns the number of AWS Config rules that are compliant and noncompliant, up to a maximum of 25 for each.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/GetComplianceSummaryByConfigRule>`_


========
Synopsis
========

::

    get-compliance-summary-by-config-rule
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the compliance summary for your AWS Config rules**

The following command returns the number of rules that are compliant and the number that are noncompliant::

    aws configservice get-compliance-summary-by-config-rule

In the output, the value for each ``CappedCount`` attribute indicates how many rules are compliant or noncompliant.

Output::

    {
        "ComplianceSummary": {
            "NonCompliantResourceCount": {
                "CappedCount": 3,
                "CapExceeded": false
            },
            "ComplianceSummaryTimestamp": 1452204131.493,
            "CompliantResourceCount": {
                "CappedCount": 2,
                "CapExceeded": false
            }
        }
    }

======
Output
======

ComplianceSummary -> (structure)

  

  The number of AWS Config rules that are compliant and the number that are noncompliant, up to a maximum of 25 for each.

  

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

    

    

  

