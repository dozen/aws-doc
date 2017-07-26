[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support refresh-trusted-advisor-check:


*****************************
refresh-trusted-advisor-check
*****************************



===========
Description
===========



Requests a refresh of the Trusted Advisor check that has the specified check ID. Check IDs can be obtained by calling  describe-trusted-advisor-checks .

 

The response contains a  TrustedAdvisorCheckRefreshStatus object, which contains these fields:

 

 
* **Status.** The refresh status of the check: "none", "enqueued", "processing", "success", or "abandoned".
 
* **MillisUntilNextRefreshable.** The amount of time, in milliseconds, until the check is eligible for refresh.
 
* **CheckId.** The unique identifier for the check.
 



========
Synopsis
========

::

    refresh-trusted-advisor-check
  --check-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--check-id`` (string)


  The unique identifier for the Trusted Advisor check.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    

  

