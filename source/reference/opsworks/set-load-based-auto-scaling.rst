[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks set-load-based-auto-scaling:


***************************
set-load-based-auto-scaling
***************************



===========
Description
===========



Specify the load-based auto scaling configuration for a specified layer. For more information, see `Managing Load with Time-based and Load-based Instances`_ .

 

.. note::

   

  To use load-based auto scaling, you must create a set of load-based auto scaling instances. Load-based auto scaling operates only on the instances from that set, so you must ensure that you have created enough instances to handle the maximum anticipated load.

   

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



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
  [--generate-cli-skeleton]




=======
Options
=======

``--layer-id`` (string)


  The layer ID.

  

``--enable`` | ``--no-enable`` (boolean)


  Enables load-based auto scaling for the layer.

  

``--up-scaling`` (structure)


  An ``down-scaling`` object with the upscaling threshold configuration. If the load exceeds these thresholds for a specified amount of time, AWS OpsWorks starts a specified number of instances.

  



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


  An ``down-scaling`` object with the downscaling threshold configuration. If the load falls below these thresholds for a specified amount of time, AWS OpsWorks stops a specified number of instances.

  



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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To set the load-based scaling configuration for a layer**

The following example enables load-based scaling for a specified layer and sets the configuration
for that layer.
You must use ``create-instance`` to add load-based instances to the layer. ::

  aws opsworks --region us-east-1 set-load-based-auto-scaling --layer-id 523569ae-2faf-47ac-b39e-f4c4b381f36d --enable --up-scaling file://upscale.json --down-scaling file://downscale.json

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

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

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Managing Load with Time-based and Load-based Instances: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-autoscaling.html
