[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional get-rate-based-rule-managed-keys:


********************************
get-rate-based-rule-managed-keys
********************************



===========
Description
===========



Returns an array of IP addresses currently being blocked by the  RateBasedRule that is specified by the ``RuleId`` . The maximum number of managed keys that will be blocked is 10,000. If more than 10,000 addresses exceed the rate limit, the 10,000 addresses with the highest rates will be blocked.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/GetRateBasedRuleManagedKeys>`_


========
Synopsis
========

::

    get-rate-based-rule-managed-keys
  --rule-id <value>
  [--next-marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule-id`` (string)


  The ``RuleId`` of the  RateBasedRule for which you want to get a list of ``ManagedKeys`` . ``RuleId`` is returned by  create-rate-based-rule and by  list-rate-based-rules .

  

``--next-marker`` (string)


  A null value and not currently used. Do not include this in your request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ManagedKeys -> (list)

  

  An array of IP addresses that currently are blocked by the specified  RateBasedRule . 

  

  (string)

    

    

  

NextMarker -> (string)

  

  A null value and not currently used.

  

  

