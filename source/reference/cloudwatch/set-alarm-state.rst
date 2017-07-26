[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch set-alarm-state:


***************
set-alarm-state
***************



===========
Description
===========



Temporarily sets the state of an alarm. When the updated ``state-value`` differs from the previous value, the action configured for the appropriate state is invoked. For example, if your alarm is configured to send an Amazon SNS message when an alarm is triggered, temporarily changing the alarm's state to **ALARM** will send an Amazon SNS message. This is not a permanent change. The next periodic alarm check (in about a minute) will set the alarm to its actual state. Because the alarm state change happens very quickly, it is typically only visibile in the alarm's **History** tab in the Amazon CloudWatch console or through ``describe-alarm-history`` . 



========
Synopsis
========

::

    set-alarm-state
  --alarm-name <value>
  --state-value <value>
  --state-reason <value>
  [--state-reason-data <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--alarm-name`` (string)


  The descriptive name for the alarm. This name must be unique within the user's AWS account. The maximum length is 255 characters. 

  

``--state-value`` (string)


  The value of the state. 

  

  Possible values:

  
  *   ``OK``

  
  *   ``ALARM``

  
  *   ``INSUFFICIENT_DATA``

  

  

``--state-reason`` (string)


  The reason that this alarm is set to this specific state (in human-readable text format) 

  

``--state-reason-data`` (string)


  The reason that this alarm is set to this specific state (in machine-readable JSON format) 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To temporarily change the state of an alarm**

The following example uses the ``set-alarm-state`` command to temporarily change the state of an
Amazon CloudWatch alarm named "myalarm" and set it to the ALARM state for testing purposes::

  aws cloudwatch set-alarm-state --alarm-name "myalarm" --state-value ALARM --state-reason "testing purposes"

This command returns to the prompt if successful.


======
Output
======

None