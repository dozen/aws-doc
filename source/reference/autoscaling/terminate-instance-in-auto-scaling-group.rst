[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling terminate-instance-in-auto-scaling-group:


****************************************
terminate-instance-in-auto-scaling-group
****************************************



===========
Description
===========



Terminates the specified instance and optionally adjusts the desired group size.

 

This call simply makes a termination request. The instance is not terminated immediately.



========
Synopsis
========

::

    terminate-instance-in-auto-scaling-group
  --instance-id <value>
  --should-decrement-desired-capacity | --no-should-decrement-desired-capacity
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-id`` (string)


  The ID of the instance.

  

``--should-decrement-desired-capacity`` | ``--no-should-decrement-desired-capacity`` (boolean)


  If ``true`` , terminating the instance also decrements the size of the Auto Scaling group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To terminate an instance in an Auto Scaling group**

This example terminates the specified instance from the specified Auto Scaling group without updating the size of the group::

	aws autoscaling terminate-instance-in-auto-scaling-group --instance-id i-93633f9b --no-should-decrement-desired-capacity

Auto Scaling launches a replacement instance after the specified instance terminates.


======
Output
======

Activity -> (structure)

  

  A scaling activity.

  

  ActivityId -> (string)

    

    The ID of the activity.

    

    

  AutoScalingGroupName -> (string)

    

    The name of the Auto Scaling group.

    

    

  Description -> (string)

    

    A friendly, more verbose description of the activity.

    

    

  Cause -> (string)

    

    The reason the activity began.

    

    

  StartTime -> (timestamp)

    

    The start time of the activity.

    

    

  EndTime -> (timestamp)

    

    The end time of the activity.

    

    

  StatusCode -> (string)

    

    The current status of the activity.

    

    

  StatusMessage -> (string)

    

    A friendly, more verbose description of the activity status.

    

    

  Progress -> (integer)

    

    A value between 0 and 100 that indicates the progress of the activity.

    

    

  Details -> (string)

    

    The details about the activity.

    

    

  

