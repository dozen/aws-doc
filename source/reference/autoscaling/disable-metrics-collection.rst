[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling disable-metrics-collection:


**************************
disable-metrics-collection
**************************



===========
Description
===========



Disables group metrics for the specified Auto Scaling group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DisableMetricsCollection>`_


========
Synopsis
========

::

    disable-metrics-collection
  --auto-scaling-group-name <value>
  [--metrics <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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