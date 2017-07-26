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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeMetricCollectionTypes>`_


========
Synopsis
========

::

    describe-metric-collection-types
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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
                "Metric": "GroupStandbyInstances"
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

      

      

    

  

