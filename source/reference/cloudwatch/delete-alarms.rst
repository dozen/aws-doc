[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch delete-alarms:


*************
delete-alarms
*************



===========
Description
===========



Deletes all specified alarms. In the event of an error, no alarms are deleted. 



========
Synopsis
========

::

    delete-alarms
  --alarm-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--alarm-names`` (list)


  A list of alarms to be deleted. 

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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