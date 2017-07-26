[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice get-compliance-summary-by-config-rule:


*************************************
get-compliance-summary-by-config-rule
*************************************



===========
Description
===========



Returns the number of AWS Config rules that are compliant and noncompliant, up to a maximum of 25 for each.



========
Synopsis
========

::

    get-compliance-summary-by-config-rule
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    

  

