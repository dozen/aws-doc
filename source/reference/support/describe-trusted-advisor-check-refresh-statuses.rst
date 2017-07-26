[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support describe-trusted-advisor-check-refresh-statuses:


***********************************************
describe-trusted-advisor-check-refresh-statuses
***********************************************



===========
Description
===========



Returns the refresh status of the Trusted Advisor checks that have the specified check IDs. Check IDs can be obtained by calling  describe-trusted-advisor-checks .

 

.. note::

   

  Some checks are refreshed automatically, and their refresh statuses cannot be retrieved by using this operation. Use of the ``describe-trusted-advisor-check-refresh-statuses`` operation for these checks causes an ``InvalidParameterValue`` error.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/support-2013-04-15/DescribeTrustedAdvisorCheckRefreshStatuses>`_


========
Synopsis
========

::

    describe-trusted-advisor-check-refresh-statuses
  --check-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--check-ids`` (list)


  The IDs of the Trusted Advisor checks to get the status of. **Note:** Specifying the check ID of a check that is automatically refreshed causes an ``InvalidParameterValue`` error.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

    

  

