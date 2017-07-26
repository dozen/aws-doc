[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support describe-trusted-advisor-check-summaries:


****************************************
describe-trusted-advisor-check-summaries
****************************************



===========
Description
===========



Returns the summaries of the results of the Trusted Advisor checks that have the specified check IDs. Check IDs can be obtained by calling  describe-trusted-advisor-checks .

 

The response contains an array of  TrustedAdvisorCheckSummary objects.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/support-2013-04-15/DescribeTrustedAdvisorCheckSummaries>`_


========
Synopsis
========

::

    describe-trusted-advisor-check-summaries
  --check-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--check-ids`` (list)


  The IDs of the Trusted Advisor checks.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

summaries -> (list)

  

  The summary information for the requested Trusted Advisor checks.

  

  (structure)

    

    A summary of a Trusted Advisor check result, including the alert status, last refresh, and number of resources examined.

    

    checkId -> (string)

      

      The unique identifier for the Trusted Advisor check.

      

      

    timestamp -> (string)

      

      The time of the last refresh of the check.

      

      

    status -> (string)

      

      The alert status of the check: "ok" (green), "warning" (yellow), "error" (red), or "not_available".

      

      

    hasFlaggedResources -> (boolean)

      

      Specifies whether the Trusted Advisor check has flagged resources.

      

      

    resourcesSummary -> (structure)

      

      Details about AWS resources that were analyzed in a call to Trusted Advisor  describe-trusted-advisor-check-summaries . 

      

      resourcesProcessed -> (long)

        

        The number of AWS resources that were analyzed by the Trusted Advisor check.

        

        

      resourcesFlagged -> (long)

        

        The number of AWS resources that were flagged (listed) by the Trusted Advisor check.

        

        

      resourcesIgnored -> (long)

        

        The number of AWS resources ignored by Trusted Advisor because information was unavailable.

        

        

      resourcesSuppressed -> (long)

        

        The number of AWS resources ignored by Trusted Advisor because they were marked as suppressed by the user.

        

        

      

    categorySpecificSummary -> (structure)

      

      Summary information that relates to the category of the check. Cost Optimizing is the only category that is currently supported.

      

      costOptimizing -> (structure)

        

        The summary information about cost savings for a Trusted Advisor check that is in the Cost Optimizing category.

        

        estimatedMonthlySavings -> (double)

          

          The estimated monthly savings that might be realized if the recommended actions are taken.

          

          

        estimatedPercentMonthlySavings -> (double)

          

          The estimated percentage of savings that might be realized if the recommended actions are taken.

          

          

        

      

    

  

