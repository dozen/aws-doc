[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling disable-metrics-collection:


**************************
disable-metrics-collection
**************************



===========
Description
===========



Disables monitoring of the specified metrics for the specified Auto Scaling group.



========
Synopsis
========

::

    disable-metrics-collection
  --auto-scaling-group-name <value>
  [--metrics <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name or Amazon Resource Name (ARN) of the group.

  

``--metrics`` (list)


  One or more of the following metrics. If you omit this parameter, all metrics are disabled.

   

   
  * ``GroupMinSize`` 
   
  * ``GroupMaxSize`` 
   
  * ``GroupDesiredCapacity`` 
   
  * ``GroupInServiceInstances`` 
   
  * ``GroupPendingInstances`` 
   
  * ``GroupStandbyInstances`` 
   
  * ``GroupTerminatingInstances`` 
   
  * ``GroupTotalInstances`` 
   

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To disable metrics collection for an Auto Scaling group**

This example disables collecting data for the ``GroupDesiredCapacity`` metric for the specified Auto Scaling group::

	aws autoscaling disable-metrics-collection --auto-scaling-group-name my-auto-scaling-group --metrics GroupDesiredCapacity

For more information, see `Monitoring Your Auto Scaling Instances and Groups`_ in the *Auto Scaling Developer Guide*.

.. _`Monitoring Your Auto Scaling Instances and Groups`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-instance-monitoring.html



======
Output
======

None