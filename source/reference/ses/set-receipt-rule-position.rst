[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses set-receipt-rule-position:


*************************
set-receipt-rule-position
*************************



===========
Description
===========



Sets the position of the specified receipt rule in the receipt rule set.

 

For information about managing receipt rules, see the `Amazon SES Developer Guide`_ .

 

This action is throttled at one request per second.



========
Synopsis
========

::

    set-receipt-rule-position
  --rule-set-name <value>
  --rule-name <value>
  [--after <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rule-set-name`` (string)


  The name of the receipt rule set that contains the receipt rule to reposition.

  

``--rule-name`` (string)


  The name of the receipt rule to reposition.

  

``--after`` (string)


  The name of the receipt rule after which to place the specified receipt rule.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======



.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-managing-receipt-rules.html
