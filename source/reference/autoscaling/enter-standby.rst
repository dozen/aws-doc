[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling enter-standby:


*************
enter-standby
*************



===========
Description
===========



Moves the specified instances into ``Standby`` mode.

 

For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling Developer Guide* .



========
Synopsis
========

::

    enter-standby
  [--instance-ids <value>]
  --auto-scaling-group-name <value>
  --should-decrement-desired-capacity | --no-should-decrement-desired-capacity
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-ids`` (list)


  One or more instances to move into ``Standby`` mode. You must specify at least one instance ID.

  



Syntax::

  "string" "string" ...



``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--should-decrement-desired-capacity`` | ``--no-should-decrement-desired-capacity`` (boolean)


  Specifies whether the instances moved to ``Standby`` mode count as part of the Auto Scaling group's desired capacity. If set, the desired capacity for the Auto Scaling group decrements by the number of instances moved to ``Standby`` mode.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To move instances into standby mode**

This example puts the specified instance into standby mode::

   aws autoscaling enter-standby --instance-ids i-93633f9b --auto-scaling-group-name my-auto-scaling-group --should-decrement-desired-capacity
   
The following is example output::

  {
    "Activities": [
        {
            "Description": "Moving EC2 instance to Standby: i-93633f9b",
            "AutoScalingGroupName": "my-auto-scaling-group",
            "ActivityId": "ffa056b4-6ed3-41ba-ae7c-249dfae6eba1",
            "Details": {"Availability Zone": "us-west-2a"},
            "StartTime": "2015-04-12T15:10:23.640Z",
            "Progress": 50,
            "Cause": "At 2015-04-12T15:10:23Z instance i-93633f9b was moved to standby in response to a user request, shrinking the capacity from 2 to 1.",
            "StatusCode": "InProgress"
        }
    ]
  }


======
Output
======

Activities -> (list)

  

  The activities related to moving instances into ``Standby`` mode.

  

  (structure)

    

    Describes scaling activity, which is a long-running process that represents a change to your Auto Scaling group, such as changing its size or replacing an instance.

    

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

      

      

    

  



.. _Auto Scaling Lifecycle: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/AutoScalingGroupLifecycle.html
