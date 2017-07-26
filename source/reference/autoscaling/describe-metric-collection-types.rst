[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-metric-collection-types:


********************************
describe-metric-collection-types
********************************



===========
Description
===========



Describes the available CloudWatch metrics for Auto Scaling.

 

Note that the ``GroupStandbyInstances`` metric is not returned by default. You must explicitly request this metric when calling  enable-metrics-collection .



========
Synopsis
========

::

    describe-metric-collection-types
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe the Auto Scaling metric collection types**

This example describes the available metric collection types::

	aws autoscaling describe-metric-collection-types

The following is example output::

  {
    "Metrics": [
      {
        "Metric": "GroupMinSize"
      },
      {
        "Metric": "GroupMaxSize"
      },
      {
        "Metric": "GroupDesiredCapacity"
      },
      {
        "Metric": "GroupInServiceInstances"
      },
      {
        "Metric": "GroupPendingInstances"
      },
      {
        "Metric": "GroupTerminatingInstances"
      },
      {
        "Metric": "GroupTotalInstances"
      }
    ],
    "Granularities": [
      {
        "Granularity": "1Minute"
      }
    ]
  }

For more information, see `Enable Auto Scaling Group Metrics`_ in the *Auto Scaling Developer Guide*.

.. _`Enable Auto Scaling Group Metrics`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-instance-monitoring.html#as-group-metrics



======
Output
======

Metrics -> (list)

  

  One or more metrics.

  

  (structure)

    

    Describes a metric.

    

    Metric -> (string)

      

      One of the following metrics:

       

       
      * ``GroupMinSize`` 
       
      * ``GroupMaxSize`` 
       
      * ``GroupDesiredCapacity`` 
       
      * ``GroupInServiceInstances`` 
       
      * ``GroupPendingInstances`` 
       
      * ``GroupStandbyInstances`` 
       
      * ``GroupTerminatingInstances`` 
       
      * ``GroupTotalInstances`` 
       

      

      

    

  

Granularities -> (list)

  

  The granularities for the metrics.

  

  (structure)

    

    Describes a granularity of a metric.

    

    Granularity -> (string)

      

      The granularity. The only valid value is ``1Minute`` .

      

      

    

  

