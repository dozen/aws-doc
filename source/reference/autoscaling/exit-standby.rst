[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling exit-standby:


************
exit-standby
************



===========
Description
===========



Moves the specified instances out of ``Standby`` mode.

 

For more information, see `Auto Scaling Lifecycle <http://docs.aws.amazon.com/autoscaling/latest/userguide/AutoScalingGroupLifecycle.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/ExitStandby>`_


========
Synopsis
========

::

    exit-standby
  [--instance-ids <value>]
  --auto-scaling-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-ids`` (list)


  One or more instance IDs. You must specify at least one instance ID.

  



Syntax::

  "string" "string" ...



``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To move instances out of standby mode**

This example moves the specified instance out of standby mode::

    aws autoscaling exit-standby --instance-ids i-93633f9b --auto-scaling-group-name my-auto-scaling-group

The following is example output::

    {
        "Activities": [
            {
                "Description": "Moving EC2 instance out of Standby: i-93633f9b",
                "AutoScalingGroupName": "my-auto-scaling-group",
                "ActivityId": "142928e1-a2dc-453a-9b24-b85ad6735928",
                "Details": {"Availability Zone": "us-west-2a"},
                "StartTime": "2015-04-12T15:14:29.886Z",
                "Progress": 30,
                "Cause": "At 2015-04-12T15:14:29Z instance i-93633f9b was moved out of standby in response to a user request, increasing the capacity from 1 to 2.",
                "StatusCode": "PreInService"
            }
        ]
    }


======
Output
======

Activities -> (list)

  

  The activities related to moving instances out of ``Standby`` mode.

  

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

      

      

    

  

