[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-load-based-auto-scaling:


********************************
describe-load-based-auto-scaling
********************************



===========
Description
===========



Describes load-based auto scaling configurations for specified layers.

 

.. note::

   

  You must specify at least one of the parameters.

   

 

 **Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeLoadBasedAutoScaling>`_


========
Synopsis
========

::

    describe-load-based-auto-scaling
  --layer-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--layer-ids`` (list)


  An array of layer IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a layer's load-based scaling configuration**

The following example describes a specified layer's load-based scaling configuration.
The layer is identified by its layer ID, which you can find on the layer's
details page or by running ``describe-layers``. ::

  aws opsworks describe-load-based-auto-scaling --region us-east-1 --layer-ids 6bec29c9-c866-41a0-aba5-fa3e374ce2a1

*Output*: The example layer has a single load-based instance. :: 

  {
    "LoadBasedAutoScalingConfigurations": [
      {
        "DownScaling": {
          "IgnoreMetricsTime": 10, 
          "ThresholdsWaitTime": 10, 
          "InstanceCount": 1, 
          "CpuThreshold": 30.0
        }, 
        "Enable": true, 
        "UpScaling": {
          "IgnoreMetricsTime": 5, 
          "ThresholdsWaitTime": 5, 
          "InstanceCount": 1, 
          "CpuThreshold": 80.0
        }, 
        "LayerId": "6bec29c9-c866-41a0-aba5-fa3e374ce2a1"
      }
    ]
  }


**More Information**

For more information, see `How Automatic Load-based Scaling Works`_ in the *AWS OpsWorks User Guide*.

.. _`How Automatic Load-based Scaling Works`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-autoscaling.html#workinginstances-autoscaling-loadbased


======
Output
======

LoadBasedAutoScalingConfigurations -> (list)

  

  An array of ``LoadBasedAutoScalingConfiguration`` objects that describe each layer's configuration.

  

  (structure)

    

    Describes a layer's load-based auto scaling configuration.

    

    LayerId -> (string)

      

      The layer ID.

      

      

    Enable -> (boolean)

      

      Whether load-based auto scaling is enabled for the layer.

      

      

    UpScaling -> (structure)

      

      An ``AutoScalingThresholds`` object that describes the upscaling configuration, which defines how and when AWS OpsWorks Stacks increases the number of instances.

      

      InstanceCount -> (integer)

        

        The number of instances to add or remove when the load exceeds a threshold.

        

        

      ThresholdsWaitTime -> (integer)

        

        The amount of time, in minutes, that the load must exceed a threshold before more instances are added or removed.

        

        

      IgnoreMetricsTime -> (integer)

        

        The amount of time (in minutes) after a scaling event occurs that AWS OpsWorks Stacks should ignore metrics and suppress additional scaling events. For example, AWS OpsWorks Stacks adds new instances following an upscaling event but the instances won't start reducing the load until they have been booted and configured. There is no point in raising additional scaling events during that operation, which typically takes several minutes. ``IgnoreMetricsTime`` allows you to direct AWS OpsWorks Stacks to suppress scaling events long enough to get the new instances online.

        

        

      CpuThreshold -> (double)

        

        The CPU utilization threshold, as a percent of the available CPU. A value of -1 disables the threshold.

        

        

      MemoryThreshold -> (double)

        

        The memory utilization threshold, as a percent of the available memory. A value of -1 disables the threshold.

        

        

      LoadThreshold -> (double)

        

        The load threshold. A value of -1 disables the threshold. For more information about how load is computed, see `Load (computing) <http://en.wikipedia.org/wiki/Load_%28computing%29>`_ .

        

        

      Alarms -> (list)

        

        Custom Cloudwatch auto scaling alarms, to be used as thresholds. This parameter takes a list of up to five alarm names, which are case sensitive and must be in the same region as the stack.

         

        .. note::

           

          To use custom alarms, you must update your service role to allow ``cloudwatch:DescribeAlarms`` . You can either have AWS OpsWorks Stacks update the role for you when you first use this feature or you can edit the role manually. For more information, see `Allowing AWS OpsWorks Stacks to Act on Your Behalf <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-servicerole.html>`_ .

           

        

        (string)

          

          

        

      

    DownScaling -> (structure)

      

      An ``AutoScalingThresholds`` object that describes the downscaling configuration, which defines how and when AWS OpsWorks Stacks reduces the number of instances.

      

      InstanceCount -> (integer)

        

        The number of instances to add or remove when the load exceeds a threshold.

        

        

      ThresholdsWaitTime -> (integer)

        

        The amount of time, in minutes, that the load must exceed a threshold before more instances are added or removed.

        

        

      IgnoreMetricsTime -> (integer)

        

        The amount of time (in minutes) after a scaling event occurs that AWS OpsWorks Stacks should ignore metrics and suppress additional scaling events. For example, AWS OpsWorks Stacks adds new instances following an upscaling event but the instances won't start reducing the load until they have been booted and configured. There is no point in raising additional scaling events during that operation, which typically takes several minutes. ``IgnoreMetricsTime`` allows you to direct AWS OpsWorks Stacks to suppress scaling events long enough to get the new instances online.

        

        

      CpuThreshold -> (double)

        

        The CPU utilization threshold, as a percent of the available CPU. A value of -1 disables the threshold.

        

        

      MemoryThreshold -> (double)

        

        The memory utilization threshold, as a percent of the available memory. A value of -1 disables the threshold.

        

        

      LoadThreshold -> (double)

        

        The load threshold. A value of -1 disables the threshold. For more information about how load is computed, see `Load (computing) <http://en.wikipedia.org/wiki/Load_%28computing%29>`_ .

        

        

      Alarms -> (list)

        

        Custom Cloudwatch auto scaling alarms, to be used as thresholds. This parameter takes a list of up to five alarm names, which are case sensitive and must be in the same region as the stack.

         

        .. note::

           

          To use custom alarms, you must update your service role to allow ``cloudwatch:DescribeAlarms`` . You can either have AWS OpsWorks Stacks update the role for you when you first use this feature or you can edit the role manually. For more information, see `Allowing AWS OpsWorks Stacks to Act on Your Behalf <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-servicerole.html>`_ .

           

        

        (string)

          

          

        

      

    

  

