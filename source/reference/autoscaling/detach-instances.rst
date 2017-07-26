[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling detach-instances:


****************
detach-instances
****************



===========
Description
===========



Removes one or more instances from the specified Auto Scaling group.

 

After the instances are detached, you can manage them independently from the rest of the Auto Scaling group.

 

If you do not specify the option to decrement the desired capacity, Auto Scaling launches instances to replace the ones that are detached.

 

If there is a Classic Load Balancer attached to the Auto Scaling group, the instances are deregistered from the load balancer. If there are target groups attached to the Auto Scaling group, the instances are deregistered from the target groups.

 

For more information, see `Detach EC2 Instances from Your Auto Scaling Group <http://docs.aws.amazon.com/autoscaling/latest/userguide/detach-instance-asg.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DetachInstances>`_


========
Synopsis
========

::

    detach-instances
  [--instance-ids <value>]
  --auto-scaling-group-name <value>
  --should-decrement-desired-capacity | --no-should-decrement-desired-capacity
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-ids`` (list)


  One or more instance IDs.

  



Syntax::

  "string" "string" ...



``--auto-scaling-group-name`` (string)


  The name of the group.

  

``--should-decrement-desired-capacity`` | ``--no-should-decrement-desired-capacity`` (boolean)


  If ``True`` , the Auto Scaling group decrements the desired capacity value by the number of instances detached.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To detach an instance from an Auto Scaling group**

This example detaches the specified instance from the specified Auto Scaling group::

    aws autoscaling detach-instances --instance-ids i-93633f9b --auto-scaling-group-name my-auto-scaling-group --should-decrement-desired-capacity

The following is example output::

    {
        "Activities": [
            {
                "Description": "Detaching EC2 instance: i-93633f9b",
                "AutoScalingGroupName": "my-auto-scaling-group",
                "ActivityId": "5091cb52-547a-47ce-a236-c9ccbc2cb2c9",
                "Details": {"Availability Zone": "us-west-2a"},
                "StartTime": "2015-04-12T15:02:16.179Z",
                "Progress": 50,
                "Cause": "At 2015-04-12T15:02:16Z instance i-93633f9b was detached in response to a user request, shrinking the capacity from 2 to 1.",
                "StatusCode": "InProgress"
            }
        ]
    }


======
Output
======

Activities -> (list)

  

  The activities related to detaching the instances from the Auto Scaling group.

  

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

      

      

    

  

