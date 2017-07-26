[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events disable-rule:


************
disable-rule
************



===========
Description
===========



Disables a rule. A disabled rule won't match any events, and won't self-trigger if it has a schedule expression.

 

 **Note:** When you make a change with this action, incoming events might still continue to match to the disabled rule. Please allow a short period of time for changes to take effect. 



========
Synopsis
========

::

    disable-rule
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the rule you want to disable.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None