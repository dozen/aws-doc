[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch enable-alarm-actions:


********************
enable-alarm-actions
********************



===========
Description
===========



Enables actions for the specified alarms. 



========
Synopsis
========

::

    enable-alarm-actions
  --alarm-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--alarm-names`` (list)


  The names of the alarms to enable actions for. 

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To enable all actions for an alarm**

The following example uses the ``enable-alarm-actions`` command to enable all actions for the alarm named myalarm.::

  aws cloudwatch enable-alarm-actions --alarm-names myalarm

This command returns to the prompt if successful.



======
Output
======

None