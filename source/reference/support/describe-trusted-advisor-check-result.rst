[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support describe-trusted-advisor-check-result:


*************************************
describe-trusted-advisor-check-result
*************************************



===========
Description
===========



Returns the results of the Trusted Advisor check that has the specified check ID. Check IDs can be obtained by calling  describe-trusted-advisor-checks .

 

The response contains a  TrustedAdvisorCheckResult object, which contains these three objects:

 

 
*  TrustedAdvisorCategorySpecificSummary 
 
*  TrustedAdvisorResourceDetail 
 
*  TrustedAdvisorResourcesSummary 
 

 

In addition, the response contains these fields:

 

 
* **Status.** The alert status of the check: "ok" (green), "warning" (yellow), "error" (red), or "not_available".
 
* **Timestamp.** The time of the last refresh of the check.
 
* **CheckId.** The unique identifier for the check.
 



========
Synopsis
========

::

    describe-trusted-advisor-check-result
  --check-id <value>
  [--language <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--check-id`` (string)


  The unique identifier for the Trusted Advisor check.

  

``--language`` (string)


  The ISO 639-1 code for the language in which AWS provides support. AWS Support currently supports English ("en") and Japanese ("ja"). Language parameters must be passed explicitly for operations that take them.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

result -> (structure)

  

  The detailed results of the Trusted Advisor check.

  

  checkId -> (string)

    

    The unique identifier for the Trusted Advisor check.

    

    

  timestamp -> (string)

    

    The time of the last refresh of the check.

    

    

  status -> (string)

    

    The alert status of the check: "ok" (green), "warning" (yellow), "error" (red), or "not_available".

    

    

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

        

        

      

    

  flaggedResources -> (list)

    

    The details about each resource listed in the check result.

    

    (structure)

      

      Contains information about a resource identified by a Trusted Advisor check. 

      

      status -> (string)

        

        The status code for the resource identified in the Trusted Advisor check.

        

        

      region -> (string)

        

        The AWS region in which the identified resource is located. 

        

        

      resourceId -> (string)

        

        The unique identifier for the identified resource.

        

        

      isSuppressed -> (boolean)

        

        Specifies whether the AWS resource was ignored by Trusted Advisor because it was marked as suppressed by the user.

        

        

      metadata -> (list)

        

        Additional information about the identified resource. The exact metadata and its order can be obtained by inspecting the  TrustedAdvisorCheckDescription object returned by the call to  describe-trusted-advisor-checks . **Metadata** contains all the data that is shown in the Excel download, even in those cases where the UI shows just summary data. 

        

        (string)

          

          

        

      

    

  

