[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events enable-rule:


***********
enable-rule
***********



===========
Description
===========



Enables a rule. If the rule does not exist, the operation fails.

 

 **Note:** When you make a change with this action, incoming events might not immediately start matching to a newly enabled rule. Please allow a short period of time for changes to take effect. 



========
Synopsis
========

::

    enable-rule
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the rule that you want to enable.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None