[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks set-load-based-auto-scaling:


***************************
set-load-based-auto-scaling
***************************



===========
Description
===========



Specify the load-based auto scaling configuration for a specified layer. For more information, see `Managing Load with Time-based and Load-based Instances <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-autoscaling.html>`_ .

 

.. note::

   

  To use load-based auto scaling, you must create a set of load-based auto scaling instances. Load-based auto scaling operates only on the instances from that set, so you must ensure that you have created enough instances to handle the maximum anticipated load.

   

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/SetLoadBasedAutoScaling>`_


========
Synopsis
========

::

    set-load-based-auto-scaling
  --layer-id <value>
  [--enable | --no-enable]
  [--up-scaling <value>]
  [--down-scaling <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--layer-id`` (string)


  The layer ID.

  

``--enable`` | ``--no-enable`` (boolean)


  Enables load-based auto scaling for the layer.

  

``--up-scaling`` (structure)


  An ``up-scaling`` object with the upscaling threshold configuration. If the load exceeds these thresholds for a specified amount of time, AWS OpsWorks Stacks starts a specified number of instances.

  



Shorthand Syntax::

    InstanceCount=integer,ThresholdsWaitTime=integer,IgnoreMetricsTime=integer,CpuThreshold=double,MemoryThreshold=double,LoadThreshold=double,Alarms=string,string




JSON Syntax::

  {
    "InstanceCount": integer,
    "ThresholdsWaitTime": integer,
    "IgnoreMetricsTime": integer,
    "CpuThreshold": double,
    "MemoryThreshold": double,
    "LoadThreshold": double,
    "Alarms": ["string", ...]
  }



``--down-scaling`` (structure)


  An ``up-scaling`` object with the downscaling threshold configuration. If the load falls below these thresholds for a specified amount of time, AWS OpsWorks Stacks stops a specified number of instances.

  



Shorthand Syntax::

    InstanceCount=integer,ThresholdsWaitTime=integer,IgnoreMetricsTime=integer,CpuThreshold=double,MemoryThreshold=double,LoadThreshold=double,Alarms=string,string




JSON Syntax::

  {
    "InstanceCount": integer,
    "ThresholdsWaitTime": integer,
    "IgnoreMetricsTime": integer,
    "CpuThreshold": double,
    "MemoryThreshold": double,
    "LoadThreshold": double,
    "Alarms": ["string", ...]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To set the load-based scaling configuration for a layer**

The following example enables load-based scaling for a specified layer and sets the configuration
for that layer.
You must use ``create-instance`` to add load-based instances to the layer. ::

  aws opsworks --region us-east-1 set-load-based-auto-scaling --layer-id 523569ae-2faf-47ac-b39e-f4c4b381f36d --enable --up-scaling file://upscale.json --down-scaling file://downscale.json

The example puts the upscaling threshold settings in a separate file in the working directory named ``upscale.json``, which contains the following. ::

  {
    "InstanceCount": 2,
    "ThresholdsWaitTime": 3,
    "IgnoreMetricsTime": 3,
    "CpuThreshold": 85,
    "MemoryThreshold": 85,
    "LoadThreshold": 85
  }
  
The example puts the downscaling threshold settings in a separate file in the working directory named ``downscale.json``, which contains the following. ::

  {
  "InstanceCount": 2,
  "ThresholdsWaitTime": 3,
  "IgnoreMetricsTime": 3,
  "CpuThreshold": 35,
  "MemoryThreshold": 30,
  "LoadThreshold": 30
  }

*Output*: None.

**More Information**

For more information, see `Using Automatic Load-based Scaling`_ in the *AWS OpsWorks User Guide*.

.. _`Using Automatic Load-based Scaling`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-autoscaling-loadbased.html



======
Output
======

None