[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch delete-alarms:


*************
delete-alarms
*************



===========
Description
===========



Deletes the specified alarms. In the event of an error, no alarms are deleted.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/DeleteAlarms>`_


========
Synopsis
========

::

    delete-alarms
  --alarm-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--alarm-names`` (list)


  The alarms to be deleted.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an alarm**

The following example uses the ``delete-alarms`` command to delete the Amazon CloudWatch alarm
named "myalarm"::

  aws cloudwatch delete-alarms --alarm-name myalarm

Output::

  This command returns to the prompt if successful.


======
Output
======

None