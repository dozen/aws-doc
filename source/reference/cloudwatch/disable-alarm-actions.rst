[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch disable-alarm-actions:


*********************
disable-alarm-actions
*********************



===========
Description
===========



Disables the actions for the specified alarms. When an alarm's actions are disabled, the alarm actions do not execute when the alarm state changes.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/DisableAlarmActions>`_


========
Synopsis
========

::

    disable-alarm-actions
  --alarm-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--alarm-names`` (list)


  The names of the alarms.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To disable actions for an alarm**

The following example uses the ``disable-alarm-actions`` command to disable all actions for the alarm named myalarm.::

  aws cloudwatch disable-alarm-actions --alarm-names myalarm

This command returns to the prompt if successful.



======
Output
======

None