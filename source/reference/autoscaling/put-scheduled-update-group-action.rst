[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling put-scheduled-update-group-action:


*********************************
put-scheduled-update-group-action
*********************************



===========
Description
===========



Creates or updates a scheduled scaling action for an Auto Scaling group. When updating a scheduled scaling action, if you leave a parameter unspecified, the corresponding value remains unchanged in the affected Auto Scaling group. 

 

For more information, see `Scheduled Scaling`_ in the *Auto Scaling Developer Guide* .



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
  [--generate-cli-skeleton]




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

   

  If you try to schedule your action in the past, Auto Scaling returns an error message. 

   

  When ``StartTime`` and ``EndTime`` are specified with ``Recurrence`` , they form the boundaries of when the recurring action starts and stops.

  

``--end-time`` (timestamp)


  The time for this action to end.

  

``--recurrence`` (string)


  The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format. For more information, see `Cron`_ in Wikipedia.

   

  When ``StartTime`` and ``EndTime`` are specified with ``Recurrence`` , they form the boundaries of when the recurring action will start and stop.

  

``--min-size`` (integer)


  The minimum size for the Auto Scaling group. 

  

``--max-size`` (integer)


  The maximum size for the Auto Scaling group. 

  

``--desired-capacity`` (integer)


  The number of EC2 instances that should be running in the group. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

.. _Cron: http://en.wikipedia.org/wiki/Cron
.. _Scheduled Scaling: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/schedule_time.html
