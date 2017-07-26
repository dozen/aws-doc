[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling put-scheduled-update-group-action:


*********************************
put-scheduled-update-group-action
*********************************



===========
Description
===========



Creates or updates a scheduled scaling action for an Auto Scaling group. When updating a scheduled scaling action, if you leave a parameter unspecified, the corresponding value remains unchanged.

 

For more information, see `Scheduled Scaling <http://docs.aws.amazon.com/autoscaling/latest/userguide/schedule_time.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/PutScheduledUpdateGroupAction>`_


========
Synopsis
========

::

    put-scheduled-update-group-action
  --auto-scaling-group-name <value>
  --scheduled-action-name <value>
  [--time <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--recurrence <value>]
  [--min-size <value>]
  [--max-size <value>]
  [--desired-capacity <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name or Amazon Resource Name (ARN) of the Auto Scaling group.

  

``--scheduled-action-name`` (string)


  The name of this scaling action.

  

``--time`` (timestamp)


  This parameter is deprecated.

  

``--start-time`` (timestamp)


  The time for this action to start, in "YYYY-MM-DDThh:mm:ssZ" format in UTC/GMT only (for example, ``2014-06-01T00:00:00Z`` ).

   

  If you specify ``Recurrence`` and ``StartTime`` , Auto Scaling performs the action at this time, and then performs the action based on the specified recurrence.

   

  If you try to schedule your action in the past, Auto Scaling returns an error message.

  

``--end-time`` (timestamp)


  The time for the recurring schedule to end. Auto Scaling does not perform the action after this time.

  

``--recurrence`` (string)


  The recurring schedule for this action, in Unix cron syntax format. For more information, see `Cron <http://en.wikipedia.org/wiki/Cron>`_ in Wikipedia.

  

``--min-size`` (integer)


  The minimum size for the Auto Scaling group.

  

``--max-size`` (integer)


  The maximum size for the Auto Scaling group.

  

``--desired-capacity`` (integer)


  The number of EC2 instances that should be running in the group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To add a scheduled action to an Auto Scaling group**

This example adds the specified scheduled action to the specified Auto Scaling group::

    aws autoscaling put-scheduled-update-group-action --auto-scaling-group-name my-auto-scaling-group --scheduled-action-name my-scheduled-action --start-time "2014-05-12T08:00:00Z" --end-time "2014-05-12T08:00:00Z" --min-size 2 --max-size 6 --desired-capacity 4

This example creates a scheduled action to scale on a recurring schedule that is scheduled to execute at 00:30 hours on the first of January, June, and December every year::

    aws autoscaling put-scheduled-update-group-action --auto-scaling-group-name my-auto-scaling-group --scheduled-action-name my-scheduled-action --recurrence "30 0 1 1,6,12 0" --min-size 2 --max-size 6 --desired-capacity 4

For more information, see `Scheduled Scaling`__ in the *Auto Scaling Developer Guide*.

.. __: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/schedule_time.html


======
Output
======

None