[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks set-time-based-auto-scaling:


***************************
set-time-based-auto-scaling
***************************



===========
Description
===========



Specify the time-based auto scaling configuration for a specified instance. For more information, see `Managing Load with Time-based and Load-based Instances`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    set-time-based-auto-scaling
  --instance-id <value>
  [--auto-scaling-schedule <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-id`` (string)


  The instance ID.

  

``--auto-scaling-schedule`` (structure)


  An ``AutoScalingSchedule`` with the instance schedule.

  



Shorthand Syntax::

    Monday={KeyName1=string,KeyName2=string},Tuesday={KeyName1=string,KeyName2=string},Wednesday={KeyName1=string,KeyName2=string},Thursday={KeyName1=string,KeyName2=string},Friday={KeyName1=string,KeyName2=string},Saturday={KeyName1=string,KeyName2=string},Sunday={KeyName1=string,KeyName2=string}




JSON Syntax::

  {
    "Monday": {"string": "string"
      ...},
    "Tuesday": {"string": "string"
      ...},
    "Wednesday": {"string": "string"
      ...},
    "Thursday": {"string": "string"
      ...},
    "Friday": {"string": "string"
      ...},
    "Saturday": {"string": "string"
      ...},
    "Sunday": {"string": "string"
      ...}
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To set the time-based scaling configuration for a layer**

The following example sets the time-based configuration for a specified instance.
You must first use ``create-instance`` to add the instance to the layer. ::

  aws opsworks --region us-east-1 set-time-based-auto-scaling --instance-id 69b6237c-08c0-4edb-a6af-78f3d01cedf2 --auto-scaling-schedule file://schedule.json

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

The example puts the schedule in a separate file in the working directory named ``schedule.json``.
For this example, the instance is on for a few hours around midday UTC (Coordinated Universal Time) on Monday and Tuesday. ::

  {
    "Monday": {
      "10": "on",
      "11": "on",
      "12": "on",
      "13": "on"
    }, 
    "Tuesday": {
      "10": "on",
      "11": "on",
      "12": "on",
      "13": "on" 
    }
  }

*Output*: None.

**More Information**

For more information, see `Using Automatic Time-based Scaling`_ in the *AWS OpsWorks User Guide*.

.. _`Using Automatic Time-based Scaling`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-autoscaling-timebased.html



======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Managing Load with Time-based and Load-based Instances: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-autoscaling.html
