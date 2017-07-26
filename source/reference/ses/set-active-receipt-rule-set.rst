[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses set-active-receipt-rule-set:


***************************
set-active-receipt-rule-set
***************************



===========
Description
===========



Sets the specified receipt rule set as the active receipt rule set.

 

.. note::

  To disable your email-receiving through Amazon SES completely, you can call this API with RuleSetName set to null.

 

For information about managing receipt rule sets, see the `Amazon SES Developer Guide`_ .

 

This action is throttled at one request per second.



========
Synopsis
========

::

    set-active-receipt-rule-set
  [--rule-set-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rule-set-name`` (string)


  The name of the receipt rule set to make active. Setting this value to null disables all email receiving.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======



.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-managing-receipt-rule-sets.html
