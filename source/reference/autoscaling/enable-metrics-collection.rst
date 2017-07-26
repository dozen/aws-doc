[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling enable-metrics-collection:


*************************
enable-metrics-collection
*************************



===========
Description
===========



Enables group metrics for the specified Auto Scaling group. For more information, see `Monitoring Your Auto Scaling Groups and Instances <http://docs.aws.amazon.com/autoscaling/latest/userguide/as-instance-monitoring.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/EnableMetricsCollection>`_


========
Synopsis
========

::

    enable-metrics-collection
  --auto-scaling-group-name <value>
  [--metrics <value>]
  --granularity <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name or ARN of the Auto Scaling group.

  

``--metrics`` (list)


  One or more of the following metrics. If you omit this parameter, all metrics are enabled.

   

   
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



``--granularity`` (string)


  The granularity to associate with the metrics to collect. The only valid value is ``1Minute`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To enable metrics collection for an Auto Scaling group**

This example enables data collection for the specified Auto Scaling group::

    aws autoscaling enable-metrics-collection --auto-scaling-group-name my-auto-scaling-group --granularity "1Minute"

To collect data for a specific metric, use the ``metrics`` parameter::

    aws autoscaling enable-metrics-collection --auto-scaling-group-name my-auto-scaling-group --metrics GroupDesiredCapacity --granularity "1Minute"

For more information, see `Monitoring Your Auto Scaling Instances and Groups`_ in the *Auto Scaling Developer Guide*.

.. _`Monitoring Your Auto Scaling Instances and Groups`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-instance-monitoring.html


======
Output
======

None