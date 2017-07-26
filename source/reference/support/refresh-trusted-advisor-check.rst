[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support refresh-trusted-advisor-check:


*****************************
refresh-trusted-advisor-check
*****************************



===========
Description
===========



Requests a refresh of the Trusted Advisor check that has the specified check ID. Check IDs can be obtained by calling  describe-trusted-advisor-checks .

 

.. note::

   

  Some checks are refreshed automatically, and they cannot be refreshed by using this operation. Use of the ``refresh-trusted-advisor-check`` operation for these checks causes an ``InvalidParameterValue`` error.

   

 

The response contains a  TrustedAdvisorCheckRefreshStatus object, which contains these fields:

 

 
* **status.** The refresh status of the check: "none", "enqueued", "processing", "success", or "abandoned". 
 
* **millisUntilNextRefreshable.** The amount of time, in milliseconds, until the check is eligible for refresh. 
 
* **checkId.** The unique identifier for the check. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/support-2013-04-15/RefreshTrustedAdvisorCheck>`_


========
Synopsis
========

::

    refresh-trusted-advisor-check
  --check-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--check-id`` (string)


  The unique identifier for the Trusted Advisor check to refresh. **Note:** Specifying the check ID of a check that is automatically refreshed causes an ``InvalidParameterValue`` error.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

status -> (structure)

  

  The current refresh status for a check, including the amount of time until the check is eligible for refresh.

  

  checkId -> (string)

    

    The unique identifier for the Trusted Advisor check.

    

    

  status -> (string)

    

    The status of the Trusted Advisor check for which a refresh has been requested: "none", "enqueued", "processing", "success", or "abandoned".

    

    

  millisUntilNextRefreshable -> (long)

    

    The amount of time, in milliseconds, until the Trusted Advisor check is eligible for refresh.

    

    

  

