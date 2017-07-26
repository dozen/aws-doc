[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support describe-trusted-advisor-check-refresh-statuses:


***********************************************
describe-trusted-advisor-check-refresh-statuses
***********************************************



===========
Description
===========



Returns the refresh status of the Trusted Advisor checks that have the specified check IDs. Check IDs can be obtained by calling  describe-trusted-advisor-checks .



========
Synopsis
========

::

    describe-trusted-advisor-check-refresh-statuses
  --check-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--check-ids`` (list)


  The IDs of the Trusted Advisor checks.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

statuses -> (list)

  

  The refresh status of the specified Trusted Advisor checks.

  

  (structure)

    

    The refresh status of a Trusted Advisor check. 

    

    checkId -> (string)

      

      The unique identifier for the Trusted Advisor check.

      

      

    status -> (string)

      

      The status of the Trusted Advisor check for which a refresh has been requested: "none", "enqueued", "processing", "success", or "abandoned".

      

      

    millisUntilNextRefreshable -> (long)

      

      The amount of time, in milliseconds, until the Trusted Advisor check is eligible for refresh.

      

      

    

  

