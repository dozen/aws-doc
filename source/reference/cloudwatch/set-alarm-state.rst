[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch set-alarm-state:


***************
set-alarm-state
***************



===========
Description
===========



Temporarily sets the state of an alarm for testing purposes. When the updated state differs from the previous value, the action configured for the appropriate state is invoked. For example, if your alarm is configured to send an Amazon SNS message when an alarm is triggered, temporarily changing the alarm state to ``ALARM`` sends an SNS message. The alarm returns to its actual state (often within seconds). Because the alarm state change happens quickly, it is typically only visible in the alarm's **History** tab in the Amazon CloudWatch console or through  describe-alarm-history .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/SetAlarmState>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--alarm-name`` (string)


  The name for the alarm. This name must be unique within the AWS account. The maximum length is 255 characters.

  

``--state-value`` (string)


  The value of the state.

  

  Possible values:

  
  *   ``OK``

  
  *   ``ALARM``

  
  *   ``INSUFFICIENT_DATA``

  

  

``--state-reason`` (string)


  The reason that this alarm is set to this specific state, in text format.

  

``--state-reason-data`` (string)


  The reason that this alarm is set to this specific state, in JSON format.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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